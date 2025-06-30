# Contributing to Sophos XG Firewall Zabbix Template

First off, thank you for considering contributing to this project! 🎉

## 🤝 Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code.

## 🚀 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples**
- **Describe the behavior you observed and expected**
- **Include screenshots if possible**
- **Include your environment details**:
  - Zabbix version
  - Sophos XG firmware version
  - SNMP version (v2c or v3)
  - Any relevant configuration

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Provide specific examples to demonstrate the enhancement**
- **Describe the current behavior and expected behavior**
- **Explain why this enhancement would be useful**

### Pull Requests

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes
4. Test your changes thoroughly
5. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
6. Push to the branch (`git push origin feature/AmazingFeature`)
7. Open a Pull Request

## 📋 Development Process

### Prerequisites

- Python 3.8+ (for testing scripts)
- Zabbix Server 7.2.0+ (for template testing)
- Access to Sophos XG Firewall (for validation)
- Basic knowledge of SNMP and Zabbix templates

### Setting Up Development Environment

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/sophos-xg-zabbix-template.git
cd sophos-xg-zabbix-template

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install development dependencies
pip install -r requirements-dev.txt
```

### Template Structure

```
sophos-xg-firewall-template.yaml
├── zabbix_export
│   ├── version: "7.2"
│   ├── template_groups
│   ├── templates
│   │   ├── items
│   │   ├── discovery_rules
│   │   ├── triggers
│   │   ├── graphs
│   │   ├── dashboards
│   │   └── macros
│   └── value_maps
```

### Testing Your Changes

1. **Syntax Validation**:
   ```bash
   python validate_template.py sophos-xg-firewall-template.yaml
   ```

2. **Import Test**:
   - Import the template into a test Zabbix instance
   - Verify no import errors occur

3. **Functional Testing**:
   - Apply template to a test host
   - Verify all items collect data
   - Test all triggers
   - Validate discovery rules

### Coding Standards

- **YAML**: Use 2 spaces for indentation
- **OIDs**: Always use numeric OIDs
- **UUIDs**: Must be valid UUID v4 format
- **Item Keys**: Use lowercase with underscores
- **Descriptions**: Clear and concise
- **Tags**: Follow Zabbix tagging best practices

### Commit Message Guidelines

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line

Examples:
```
Add discovery rule for SSL VPN users

- Create new discovery rule using sfosSSLVpnUserName OID
- Add item prototypes for user connection status
- Include trigger for disconnected users
- Update documentation with new metrics

Fixes #123
```

## 📚 Documentation

- Update README.md if you change functionality
- Add comments to complex configurations
- Update the changelog for significant changes
- Include examples for new features

## 🔧 Adding New Features

### Adding New Items

1. Find the appropriate OID in the MIB file
2. Add item definition to template
3. Set appropriate:
   - Update interval
   - History retention
   - Trend retention
   - Value mapping (if applicable)
   - Preprocessing (if needed)
   - Tags

### Adding Discovery Rules

1. Identify the discovery OID
2. Create discovery rule with appropriate filter
3. Add item prototypes
4. Add trigger prototypes (if needed)
5. Add graph prototypes (if applicable)

### Adding Triggers

1. Use appropriate severity levels:
   - **Disaster**: Service completely down
   - **High**: Service degraded
   - **Average**: Warning conditions
   - **Warning**: Informational
   - **Info**: State changes

2. Include recovery expressions
3. Add meaningful descriptions
4. Use macros for thresholds

## 🎯 Priority Areas

Current areas where contributions are especially welcome:

- [ ] SNMPv3 enhanced support
- [ ] Additional dashboard widgets
- [ ] Performance optimization
- [ ] Additional language translations
- [ ] Automated testing scripts
- [ ] Grafana dashboard export

## 📞 Getting Help

- **GitHub Issues**: For bugs and feature requests
- **Email**: info@pinet.com.tr
- **Documentation**: Check the README and Wiki

## 🏆 Recognition

Contributors will be recognized in:
- The project README
- Release notes
- GitHub contributors page

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to make this template better! 🙏 