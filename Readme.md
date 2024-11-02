# DevOps Assignment Report
## Docker Application Debugging and Deployment

### Issues Identified

#### 1. Python Application Container Issues
- **Dockerfile Syntax Errors:**
  - Incorrect working directory path (`/appp` instead of `/app`)
  - Wrong source file name in COPY command (`appy.py` instead of `app.py`)
  - Incorrect package name in pip install (`netiface` instead of `netifaces`)
  - Port exposure using text instead of number (`"eight thousand"`)
  - Python command typo in CMD directive (`pythn`)

#### 2. Nginx Container Issues
- **Dockerfile Configuration Errors:**
  - Invalid base image tag (`nginx:latests`)
  - Incorrect configuration file name (`nginix.conf`)
  - Wrong HTML directory path (`htmll`)
  - Text instead of number for port exposure (`"eighty"`)
  - Incorrect daemon flag syntax (`daemon of`)

- **Nginx Configuration File Errors:**
  - Syntax error in worker processes directive
  - Incorrect worker connections spelling
  - Wrong MIME types file path
  - Missing semicolons in configuration
  - Typo in default_type directive

#### 3. Docker Compose Issues
- **Configuration Errors:**
  - Mismatched image names with built images
  - Port mapping using text instead of numbers
  - Incorrect volume mounting path for nginx.conf
  - Wrong network driver specification
  - Unnecessary complex network options
- **Runtime Error:**
  - Port 80 binding permission issues on Windows

### Resolution Steps

#### 1. Python Application Fixes
1. **Dockerfile Corrections:**
   - Fixed working directory to `/app`
   - Corrected file name in COPY command
   - Updated package name to `netifaces`
   - Changed port exposure to numeric value `8000`
   - Fixed Python command in CMD

2. **Application Verification:**
   - Successfully built Python container
   - Verified Flask application accessibility
   - Confirmed proper package installation

#### 2. Nginx Configuration Fixes
1. **Dockerfile Updates:**
   - Corrected base image to `nginx:latest`
   - Fixed configuration file paths
   - Updated HTML directory location
   - Changed port exposure to numeric value `80`
   - Corrected daemon flag to `daemon off`

2. **Configuration File Corrections:**
   - Fixed worker processes syntax
   - Corrected worker connections directive
   - Updated MIME types path
   - Added missing semicolons
   - Fixed default_type specification

#### 3. Docker Compose Solutions
1. **Configuration Updates:**
   - Aligned image names with built containers
   - Corrected port mappings to numeric values
   - Fixed volume mount paths
   - Simplified network configuration
   - Added service dependencies

2. **Port Binding Resolution:**
   - Changed application port from 80 to 8080 to avoid Windows permission issues
   - Updated nginx configuration to reflect new port mapping
   - Verified accessibility through new port

### Final Implementation Results
- Successfully built and deployed both containers
- Established proper communication between Nginx and Python services
- Confirmed application accessibility through web browser
- Verified proper logging and monitoring
- Ensured system stability and proper error handling

### Additional Notes
- All source code and configurations have been documented in the GitHub repository
- Application successfully displays user information including IP address, MAC address, username, and timestamp
- Nginx properly forwards requests to the Python backend service
- All containers are properly networked using Docker's bridge networking
