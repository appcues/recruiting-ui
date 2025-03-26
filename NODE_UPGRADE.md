# Node.js LTS Upgrade

This project has been upgraded to use Node.js 20.x (the latest LTS version as of 2023). This document outlines the changes made and provides guidance for developers.

## Changes Made

1. **Updated Node.js Version Requirement**

   - Changed `engines` field in `package.json` to require Node.js >=20.0.0
   - Added `.nvmrc` file with Node.js 20 specification for nvm users

2. **Dependency Updates**

   - Updated `react-scripts` from 4.0.1 to 5.0.1 for compatibility
   - Added `semver` for Node.js version checking
   - Added `@testing-library/react-hooks` for testing custom hooks

3. **Version Verification**
   - Added a Node.js version verification script (`scripts/check-node-version.js`)
   - Added a prestart hook to verify Node.js version before starting the app

## Upgrading Your Development Environment

### Using nvm (recommended)

If you use [nvm](https://github.com/nvm-sh/nvm), you can simply run:

```bash
nvm install
nvm use
```

The `.nvmrc` file will ensure you're using the correct version.

### Without nvm

If you're not using nvm, please ensure you have Node.js 20.x installed. You can download it from the [official Node.js website](https://nodejs.org/).

## Potential Issues

### Incompatible Dependencies

If you encounter errors related to incompatible dependencies during installation, you can use:

```bash
npm install --legacy-peer-deps
```

This is mentioned in the original README as well.

### React Scripts Issues

The upgrade from react-scripts 4.0.1 to 5.0.1 should be backward compatible, but if you encounter any issues:

1. Clear your node_modules and reinstall:

   ```bash
   rm -rf node_modules
   npm install
   ```

2. If that doesn't work, try clearing the cache:
   ```bash
   npm cache clean --force
   ```
