# Warranty System Setup Guide

## Quick Fix for Shop Creation Issue

The main issue is that **MongoDB is not running** on your system. Here are the solutions:

### Option 1: Use MongoDB Atlas (Recommended - Free Cloud Database)

1. **Go to MongoDB Atlas**: https://www.mongodb.com/atlas
2. **Create a free account** and cluster
3. **Get your connection string** from the cluster
4. **Create a `.env` file** in your project root with:
   ```
   MONGODB_URI=your_mongodb_atlas_connection_string
   JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
   ```

### Option 2: Install MongoDB Locally

1. **Download MongoDB Community Server**: https://www.mongodb.com/try/download/community
2. **Install it** on your Windows system
3. **Start MongoDB service**:
   - Open Services (Win + R, type `services.msc`)
   - Find "MongoDB" service and start it
   - Or run: `net start MongoDB`

### Option 3: Use Docker (if you have Docker)

```bash
docker run -d -p 27017:27017 --name mongodb mongo:latest
```

## Testing the Fix

1. **Stop your current server** (Ctrl+C)
2. **Start the server again**:
   ```bash
   npm run dev:server
   ```
3. **You should see**: "Connected to MongoDB" instead of the error
4. **Try adding a shop** - it should work now!

## Troubleshooting

- **If you still get connection errors**: Make sure MongoDB is running on port 27017
- **If the form still doesn't submit**: Check the browser console for errors
- **If you get validation errors**: Make sure all fields are filled out

## Admin Login

- **Username**: admin
- **Password**: admin123

## Need Help?

If you're still having issues, try:
1. Check the browser console (F12) for errors
2. Check the server console for error messages
3. Make sure both frontend and backend are running 