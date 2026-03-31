# Entity Relationship Diagram (ERD)

This document describes the database schema and relationships for Dashboard Hub.

## Core Entities

### Users
```
Users
├── id (PK)
├── email (UNIQUE)
├── password_hash
├── first_name
├── last_name
├── role_id (FK)
├── is_active
├── created_at
└── updated_at
```

### Roles
```
Roles
├── id (PK)
├── name
├── description
├── permissions (JSON)
├── created_at
└── updated_at
```

## Dashboard Entities

### Dashboards
```
Dashboards
├── id (PK)
├── user_id (FK)
├── name
├── description
├── layout (JSON)
├── is_public
├── created_at
└── updated_at
```

### Widgets
```
Widgets
├── id (PK)
├── dashboard_id (FK)
├── widget_type
├── title
├── configuration (JSON)
├── position
├── size
├── created_at
└── updated_at
```

### Data Sources
```
DataSources
├── id (PK)
├── user_id (FK)
├── name
├── type
├── connection_details (JSON)
├── is_active
├── created_at
└── updated_at
```

## Analytics Entities

### Metrics
```
Metrics
├── id (PK)
├── dashboard_id (FK)
├── name
├── calculation
├── unit
├── target_value
├── created_at
└── updated_at
```

### Reports
```
Reports
├── id (PK)
├── user_id (FK)
├── name
├── template
├── configuration (JSON)
├── schedule (JSON)
├── created_at
└── updated_at
```

### Report Executions
```
ReportExecutions
├── id (PK)
├── report_id (FK)
├── execution_date
├── status
├── output_file
├── created_at
└── updated_at
```

## Collaboration Entities

### Shares
```
Shares
├── id (PK)
├── dashboard_id (FK)
├── shared_with_user_id (FK)
├── permission_level
├── created_at
└── updated_at
```

### Comments
```
Comments
├── id (PK)
├── dashboard_id (FK)
├── user_id (FK)
├── content
├── created_at
└── updated_at
```

### Activity Log
```
ActivityLog
├── id (PK)
├── user_id (FK)
├── dashboard_id (FK)
├── action
├── details (JSON)
├── created_at
└── updated_at
```

## Relationships

### One-to-Many
- Users → Dashboards
- Users → DataSources
- Users → Reports
- Dashboards → Widgets
- Dashboards → Metrics
- Dashboards → Comments
- Dashboards → Shares
- Reports → ReportExecutions
- DataSources → Widgets

### Many-to-Many
- Users ↔ Dashboards (through Shares)
- Users ↔ Roles (through UserRoles)

## Indexes

Key indexes for performance:

```sql
-- Users
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_role_id ON users(role_id);

-- Dashboards
CREATE INDEX idx_dashboards_user_id ON dashboards(user_id);
CREATE INDEX idx_dashboards_is_public ON dashboards(is_public);

-- Widgets
CREATE INDEX idx_widgets_dashboard_id ON widgets(dashboard_id);

-- DataSources
CREATE INDEX idx_datasources_user_id ON datasources(user_id);

-- Metrics
CREATE INDEX idx_metrics_dashboard_id ON metrics(dashboard_id);

-- Reports
CREATE INDEX idx_reports_user_id ON reports(user_id);

-- Shares
CREATE INDEX idx_shares_dashboard_id ON shares(dashboard_id);
CREATE INDEX idx_shares_user_id ON shares(shared_with_user_id);

-- Comments
CREATE INDEX idx_comments_dashboard_id ON comments(dashboard_id);
CREATE INDEX idx_comments_user_id ON comments(user_id);

-- ActivityLog
CREATE INDEX idx_activity_user_id ON activity_log(user_id);
CREATE INDEX idx_activity_dashboard_id ON activity_log(dashboard_id);
```

## Data Integrity

### Constraints
- Foreign key constraints for referential integrity
- Unique constraints on business keys
- Check constraints for valid values
- Not null constraints on required fields

### Triggers
- Automatic timestamp updates
- Activity log creation
- Notification triggers
- Audit log maintenance

## Related Documentation

- [STRUCTURE](./STRUCTURE.md) - Project structure
- [TECHNOLOGIES](./TECHNOLOGIES.md) - Technology stack
- [DEPLOYMENT](./DEPLOYMENT.md) - Deployment guide
