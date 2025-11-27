# My Monorepo

A monorepo containing multiple Next.js applications and shared packages.

## Project Structure

The monorepo contains:

- Three frontend sites: `site1`, `site2`, and `site3` 
- An admin dashboard: `admin`
- Shared packages:
  - `ui`: Shared UI components
  - `shared`: Shared utilities, constants, and API client
  - `database`: Prisma database access and services

## Data Linking and Sharing Implementation

The system now supports profile sharing between sites. Users can create profiles on their site and choose to share them with other sites. The admin panel provides a central place to manage all profiles and their sharing settings.

### Key Features

1. **Cross-Site Data Sharing**: Profiles created on one site can be shared with other sites
2. **Central Administration**: Admin panel allows viewing, editing, and managing all profiles and customers
3. **Seamless Integration**: Each site displays both its own profiles and profiles shared from other sites
4. **Data Analytics**: Admin dashboard shows statistics about profile distribution and sharing

### Technical Implementation

- **Prisma Schema**: Database schema with relationships between customers, profiles, and sites
- **Database Services**: Service layer to manage database operations and data sharing logic
- **Shared API Client**: Common API client used across all sites for consistent data handling
- **REST API Routes**: API routes in each application for data access and management

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Set up the database:
```bash
npx prisma generate --schema=packages/database/prisma/schema.prisma
npx prisma db push --schema=packages/database/prisma/schema.prisma
npx prisma db seed --schema=packages/database/prisma/schema.prisma
```

3. Start the development server:
```bash
npm run dev
```

## Testing Data Synchronization

To test the data linking and synchronization between sites:

1. **Create Profiles with Sharing Enabled**:
   - Go to Site 1 (http://localhost:3001)
   - Add a new profile and check the boxes to share with Site 2 and/or Site 3
   - Similarly, create profiles on Site 2 and Site 3 with sharing enabled

2. **View Shared Profiles**:
   - Navigate to each site and verify that profiles shared from other sites appear under "Shared With You" section
   - Confirm the source site is correctly indicated on the shared profiles

3. **Admin Management**:
   - Access the Admin dashboard (http://localhost:3000)
   - Go to the Profiles page to see all profiles across all sites
   - Try filtering profiles by site
   - Use the Data page to view analytics on profile sharing

4. **Profile Editing and Sharing Management**:
   - From the Admin panel, edit profiles and their sharing settings
   - Verify that changes are reflected across all relevant sites
   - Test adding a new profile from Admin and share it with selected sites

## Application URLs

- Admin: [http://localhost:3000](http://localhost:3000)
- Site 1: [http://localhost:3001](http://localhost:3001)
- Site 2: [http://localhost:3002](http://localhost:3002)
- Site 3: [http://localhost:3003](http://localhost:3003)
# monorepo
