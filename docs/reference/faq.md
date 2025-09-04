# Frequently Asked Questions

Common questions and answers about our engineering standards, processes, and tools.

## General Questions

### Q: Who should follow these engineering standards?
**A:** All engineering team members across all business units (Web, Mobile, Cloud, AI, and Data Engineering) should follow these standards. This includes:
- Full-time employees
- Contractors and consultants
- Interns and junior developers
- External team members working on our projects

### Q: What happens if I don't follow the standards?
**A:** Our standards exist to ensure code quality, security, and maintainability. While we understand that exceptions may be necessary, consistent non-compliance may result in:
- Code review rejections
- Additional training requirements
- Performance review discussions
- In serious cases, project reassignment

If you need an exception, please follow our [exception process](index.md#exception-process).

### Q: How often are these standards updated?
**A:** Standards are reviewed and updated on a regular basis:
- **Minor updates**: As needed when new tools or practices are adopted
- **Major reviews**: Quarterly with the architecture team
- **Annual review**: Comprehensive review of all standards
- **Emergency updates**: For critical security or compliance changes

You can track changes in our [changelog](changelog.md).

### Q: I'm new to the team. Where should I start?
**A:** Welcome! Follow this path:
1. Complete the [Getting Started guide](../getting-started/index.md)
2. Set up your [development environment](../getting-started/development-environment.md)
3. Review your [business unit standards](../developer-guide/index.md)
4. Complete the [first steps guide](../getting-started/first-steps.md)
5. Find a mentor on your team

## Technical Questions

### Q: Which programming languages are approved for use?
**A:** Approved languages by business unit:

**Web Development:**
- JavaScript/TypeScript (preferred)
- Python (for backend services)
- Go (for high-performance services)

**Mobile Development:**
- Swift (iOS)
- Kotlin (Android)
- JavaScript/TypeScript (React Native)
- Dart (Flutter)

**Cloud Engineering:**
- Go (preferred for infrastructure tools)
- Python (for automation scripts)
- Bash/Shell (for simple scripts)

**AI Engineering:**
- Python (primary)
- R (for statistical analysis)
- Scala (for big data processing)

**Data Engineering:**
- Python (primary)
- SQL (all dialects)
- Scala (for Spark jobs)

### Q: Can I use a different framework than what's listed in the standards?
**A:** New frameworks require approval through our technology evaluation process:
1. Create an RFC (Request for Comments) document
2. Present to the architecture team
3. Conduct a pilot project if approved
4. Update standards if the pilot is successful

For urgent needs, discuss with your team lead.

### Q: What are the minimum testing requirements?
**A:** All code must meet these minimum testing requirements:
- **Unit tests**: 80% code coverage minimum
- **Integration tests**: All API endpoints and database interactions
- **End-to-end tests**: Critical user journeys
- **Security tests**: Vulnerability scanning for all applications
- **Performance tests**: Load testing for production services

See [Testing Standards](../developer-guide/web/testing.md) for details.

### Q: How do I handle secrets and environment variables?
**A:** Follow these practices:
- **Never commit secrets** to version control
- Use environment variables for configuration
- Store secrets in approved secret management tools
- Use different secrets for each environment
- Rotate secrets regularly

See [Security Architecture](../architecture/security.md) for detailed guidance.

## Process Questions

### Q: What's the code review process?
**A:** All code changes must go through this process:
1. Create a feature branch from main
2. Make your changes with appropriate tests
3. Run all quality checks locally
4. Create a pull request with a clear description
5. Request review from at least one team member
6. Address all feedback and re-request review
7. Merge after approval (squash merge preferred)

See [First Steps](../getting-started/first-steps.md#step-7-create-pull-request) for details.

### Q: How long should code reviews take?
**A:** Our targets are:
- **Initial review**: Within 24 hours
- **Follow-up reviews**: Within 4 hours
- **Small changes** (<50 lines): Within 2 hours
- **Large changes** (>500 lines): May take 48+ hours

If reviews are taking longer, discuss with your team lead.

### Q: When should I create an ADR (Architectural Decision Record)?
**A:** Create an ADR for decisions that:
- Affect multiple teams or systems
- Have long-term implications
- Involve significant cost or effort
- Change our technology stack
- Impact security or compliance
- Set precedents for future decisions

See [Architectural Decisions](../architecture/decisions.md) for templates.

### Q: How do we handle incident response?
**A:** For production incidents:
1. **Immediate**: Alert the on-call engineer
2. **Assessment**: Determine severity and impact
3. **Response**: Follow incident response runbooks
4. **Communication**: Update stakeholders regularly
5. **Resolution**: Fix the immediate problem
6. **Post-mortem**: Conduct blameless post-mortem

See [Operations](../operations/troubleshooting.md) for detailed procedures.

## Tool and Technology Questions

### Q: Which IDE should I use?
**A:** Recommended IDEs by business unit:
- **Visual Studio Code**: Universal recommendation with extensions
- **WebStorm**: For intensive JavaScript/TypeScript development
- **PyCharm**: For Python-heavy development (AI/Data teams)
- **IntelliJ IDEA**: For Java/Kotlin development
- **Xcode**: Required for iOS development
- **Android Studio**: Required for Android development

See [Development Environment](../getting-started/development-environment.md) for setup guides.

### Q: What databases can I use?
**A:** Approved databases:

**Relational:**
- PostgreSQL (preferred for new projects)
- MySQL (existing projects only)
- SQLite (development/testing only)

**NoSQL:**
- MongoDB (document storage)
- Redis (caching and sessions)
- Elasticsearch (search and analytics)

**Cloud Databases:**
- AWS RDS, Aurora
- Azure Database services
- Google Cloud SQL, Firestore

### Q: How do I request access to cloud resources?
**A:** Cloud access requests:
1. Submit request through internal ticketing system
2. Include business justification
3. Specify required permissions (least privilege)
4. Get manager approval
5. Complete security training if required
6. Access will be provisioned within 2 business days

Contact the Cloud Engineering team for assistance.

### Q: Can I use AI coding assistants like GitHub Copilot?
**A:** Yes, with these guidelines:
- **Approved tools**: GitHub Copilot, AWS CodeWhisperer (with enterprise accounts)
- **Review all generated code** for security and quality
- **Don't commit** code you don't understand
- **Follow existing patterns** and standards
- **Test thoroughly** as AI-generated code may have subtle issues

## Deployment and Operations

### Q: How often should we deploy to production?
**A:** Deployment frequency targets:
- **Web applications**: Multiple times per day
- **Mobile applications**: Weekly to bi-weekly (app store constraints)
- **Infrastructure**: As needed, with proper change management
- **ML models**: Based on model performance metrics
- **Data pipelines**: Daily or as data requirements change

### Q: What environments do we maintain?
**A:** Standard environments:
- **Development**: Local development and feature branches
- **Testing**: Automated testing and QA validation
- **Staging**: Production-like environment for final testing
- **Production**: Live environment serving users

Some teams may have additional environments for specific needs.

### Q: How do I roll back a deployment?
**A:** Rollback procedures:
1. **Immediate**: Use deployment tool's rollback feature
2. **Database changes**: Follow database rollback procedures
3. **Feature flags**: Disable problematic features
4. **Communication**: Notify stakeholders
5. **Investigation**: Determine root cause
6. **Fix forward**: Prepare proper fix for next deployment

See [Deployment Procedures](../operations/deployment.md) for details.

## Business Unit Specific Questions

### Web Development

**Q: React vs Vue.js - which should I choose for new projects?**

**A:** Both are approved, but consider:
- **React**: Larger ecosystem, more team experience, better TypeScript support
- **Vue.js**: Easier learning curve, better single-file components, lighter bundle
- **Team expertise**: Choose based on team familiarity
- **Project requirements**: Consider specific needs

Discuss with your team lead for project-specific recommendations.

**Q: Should I use a CSS framework?**

**A:** Recommended CSS approaches:
- **Tailwind CSS**: Preferred for new projects
- **CSS Modules**: Good for component-specific styles
- **Styled Components**: Acceptable for React projects
- **SASS/SCSS**: For complex styling needs

Avoid large frameworks like Bootstrap unless specifically needed.

### Mobile Development

**Q: Native vs Cross-platform - how do I decide?**

**A:** Decision matrix:

**Choose Native when:**
- Heavy use of platform-specific features
- Maximum performance is critical
- Team has strong native expertise
- Budget allows for separate codebases

**Choose Cross-platform when:**
- Need to ship quickly to both platforms
- Limited mobile development resources
- App is content/form-heavy rather than feature-rich
- Want to maintain single codebase

**Q: Which cross-platform framework should I use?**

**A:** Current recommendations:
- **React Native**: If team has React experience
- **Flutter**: For high-performance, custom UI requirements
- **Cordova/PhoneGap**: Not recommended for new projects

### Cloud Engineering

**Q: Which cloud provider should I use?**

**A:** Multi-cloud strategy:
- **AWS**: Primary cloud provider for most services
- **Azure**: For Microsoft-integrated solutions
- **Google Cloud**: For AI/ML and data analytics workloads
- **Multi-cloud**: Avoid unless specifically required

Discuss with Cloud Engineering team for project-specific needs.

**Q: Docker vs Podman - which container runtime?**

**A:** Current policy:
- **Docker**: Standard for development and most production workloads
- **Podman**: Acceptable alternative, especially for security-sensitive environments
- **containerd**: For Kubernetes environments

### AI Engineering

**Q: TensorFlow vs PyTorch - which ML framework?**

**A:** Framework selection:
- **PyTorch**: Preferred for research and experimentation
- **TensorFlow**: Good for production deployments
- **Scikit-learn**: For traditional ML algorithms
- **Choose based on**: Team expertise and project requirements

**Q: How do I deploy ML models to production?**

**A:** Deployment options:
- **MLflow**: For model versioning and deployment
- **Kubernetes**: For scalable model serving
- **AWS SageMaker**: For AWS-integrated solutions
- **REST APIs**: For simple model serving

See [AI Standards](../developer-guide/ai/index.md) for detailed guidance.

### Data Engineering

**Q: Airflow vs Prefect - which workflow orchestrator?**

**A:** Current recommendations:
- **Apache Airflow**: Standard for most data pipelines
- **Prefect**: For more dynamic workflows
- **Choose based on**: Complexity and team preferences

**Q: How do I handle data quality issues?**

**A:** Data quality framework:
1. **Validation**: Implement data validation at ingestion
2. **Monitoring**: Set up data quality alerts
3. **Documentation**: Maintain data dictionaries
4. **Testing**: Include data tests in pipelines
5. **Governance**: Follow data governance policies

## Getting More Help

### Q: I have a question not covered in this FAQ. Where can I get help?
**A:** Help resources in order of preference:
1. **Search this documentation** - Use the search feature
2. **Team Slack channels** - Ask your team first
3. **Office hours** - Attend weekly office hours
4. **Team leads** - Contact your business unit lead
5. **Architecture team** - For architectural questions
6. **Create an issue** - For documentation improvements

### Q: How can I contribute to improving these standards?
**A:** We welcome contributions:
1. **Identify issues** - Notice problems or gaps
2. **Propose solutions** - Create RFC documents
3. **Update documentation** - Submit pull requests
4. **Share knowledge** - Present at tech talks
5. **Provide feedback** - Participate in reviews

See [Contributing Guide](contributing.md) for detailed instructions.

### Q: Who maintains this documentation?
**A:** Documentation maintenance:
- **Overall ownership**: Engineering Leadership Team
- **Day-to-day updates**: All engineering team members
- **Major changes**: Architecture team with leadership approval
- **Business unit sections**: Respective team leads

---

**Still have questions?**

- Check our [Glossary](glossary.md) for term definitions
- Review [Resources](resources.md) for additional learning materials  
- Contact your team lead or post in team Slack channels
- [Open an issue](https://github.com/rcdelacruz/engineering-standards-guide/issues) for documentation improvements

**Office Hours Schedule:**
- Architecture Q&A: Tuesdays 2:00 PM GMT+8
- Web Development: Wednesdays 10:00 AM GMT+8  
- Mobile Development: Thursdays 3:00 PM GMT+8
- Cloud Engineering: Fridays 1:00 PM GMT+8
- AI/Data Engineering: Mondays 4:00 PM GMT+8