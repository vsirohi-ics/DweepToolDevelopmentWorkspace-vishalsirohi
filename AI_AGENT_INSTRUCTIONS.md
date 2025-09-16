# AI Agent Instructions for DweepToolDevelopmentWorkspace-vishalsirohi

## CRITICAL: Follow ICS Standards

You MUST follow all standards in `ICSCoreStandards/` directory.

## Multi-Repository Workspace Structure

This workspace supports multiple packages/repositories organized by layer:

### Repository Organization
- **Data Access Layer**: `packages/data-access-layer/`
- **Business Layer**: `packages/business-layer/`
- **API Layer**: `packages/api-layer/`
- **Presentation Layer**: `packages/presentation-layer/`
- **Shared**: `packages/shared/`

### Repository Creation Rules
- MUST ask for approval before creating new repositories
- MUST follow naming convention: `{component}-{layer}`
- MUST place repositories in appropriate layer directories
- MUST document inter-repository dependencies

## Development Process

### Phase 1: System-Wide Specification Creation
1. **MUST** create system-wide specifications in `specifications/`:
   - System Architecture Specification
   - Cross-Component Integration Specification
   - Shared Data Model Specifications
   - API Contract Specifications

2. **MUST** get approval for each specification before proceeding

### Phase 2: Repository-Specific Specifications
For each repository in `packages/`:
1. **MUST** create repository-specific specifications:
   - Component API Model Specification
   - Component Architecture Specification
   - Component Design Specification
   - Component Data Model Specification

2. **MUST** ensure specifications align with system-wide specifications

### Phase 3: Interface Generation
1. **MUST** generate shared interfaces in `packages/shared/`:
   - Cross-layer communication interfaces
   - Common type definitions
   - Shared contract specifications

2. **MUST** finalize all contracts before implementation

### Phase 4: Layer Implementation
1. **MUST** implement repositories in layer order:
   - Data Access Layer repositories
   - Business Logic Layer repositories
   - API Layer repositories
   - Presentation Layer repositories

2. **MUST** maintain layer boundaries between repositories

## Repository Management

### Creating New Repositories
```bash
# Ask for approval first
# Then create in appropriate layer directory
cd packages/{layer}/
mkdir {component}-{layer}
cd {component}-{layer}
git init
```

### Repository Dependencies
- MUST document dependencies between repositories
- MUST use semantic versioning for repository releases
- MUST maintain compatibility matrices
- MUST NOT create circular dependencies

## Technology Stack (Approved)

### Backend Repositories:
- Java 17+ with Spring Boot
- PostgreSQL for data persistence
- Redis for caching

### Frontend Repositories:
- React 18+ with TypeScript
- Next.js for SSR/SSG
- Tailwind CSS for styling

### Shared Libraries:
- Common type definitions
- Utility libraries
- Interface specifications

## Layer Constraints (Per Repository)

### Data Access Layer Repositories
- MUST only import: Data Models, Abstract Data Types, Infrastructure libs
- MUST NOT import: API Models, Business Layer, Presentation Layer
- MUST provide ADT instances to Business Layer

### Business Layer Repositories
- MUST only import: Abstract Data Types, Common Types, Shared interfaces
- MUST NOT import: Data Models, API Models, Presentation Layer
- MUST be framework-agnostic

### API Layer Repositories
- MUST only import: API Models, Common Types, Shared interfaces
- MUST NOT import: Data Models, Business Layer implementation
- MUST provide semantic validation

### Presentation Layer Repositories
- MUST only communicate through API Layer
- MUST NOT directly access Business or Data Access layers
- MUST implement proper separation of concerns

### Shared Repositories
- MUST contain only: Common Types, Interfaces, Utilities
- MUST NOT contain layer-specific implementation
- MUST be importable by multiple layers (where allowed)

## Commands to Run

### Initial System Setup:
```bash
cd DweepToolDevelopmentWorkspace-vishalsirohi
q chat "Create system-wide specifications for service with multi-repository architecture following ICS standards"
```

### Repository Creation:
```bash
q chat "Create new repository for {component} in {layer} following ICS standards and system specifications"
```

### Cross-Repository Integration:
```bash
q chat "Generate shared interfaces for cross-repository communication following approved specifications"
```

### Repository Implementation:
```bash
q chat "Implement {repository-name} following layer constraints and approved specifications"
```

## Multi-Repository Validation

### Before Creating New Repository:
- [ ] Repository purpose clearly defined
- [ ] Layer placement appropriate
- [ ] Dependencies documented
- [ ] Naming convention followed
- [ ] Team approval obtained

### Before Cross-Repository Changes:
- [ ] Impact analysis completed
- [ ] Interface compatibility maintained
- [ ] Version compatibility verified
- [ ] Integration tests updated

### Before Repository Integration:
- [ ] Layer boundaries maintained
- [ ] Only approved interfaces used
- [ ] Dependencies properly managed
- [ ] Integration tests passing

## Repository Approval Process

1. **System Design**: Create system-wide specifications
2. **Repository Planning**: Define repository structure and dependencies
3. **Team Approval**: Get approval for repository creation
4. **Repository Creation**: Create repository in appropriate layer
5. **Specification Creation**: Create repository-specific specifications
6. **Implementation**: Follow layer constraints and use approved interfaces

**Remember: Each repository MUST follow ICS layer architecture standards and maintain proper boundaries!**
