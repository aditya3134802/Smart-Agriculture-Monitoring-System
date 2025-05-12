# Smart Agriculture Monitoring System

<div align="center">
  <img src="docs/images/smart-agriculture-logo.png" alt="Smart Agriculture Logo" width="300"/>
  <h3>🌱 IoT-Based Agricultural Monitoring and Management Platform 🌱</h3>
  <p>Leveraging AWS cloud services to revolutionize precision farming through real-time monitoring, analytics, and intelligent decision support</p>
  
  ![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
  ![Version](https://img.shields.io/badge/version-1.0.0-blue)
  ![AWS](https://img.shields.io/badge/AWS-IoT%20Core%20%7C%20Lambda%20%7C%20DynamoDB-orange)
  ![IaC](https://img.shields.io/badge/IaC-Terraform-purple)
  ![License](https://img.shields.io/badge/license-MIT-green)
</div>

## 📋 Overview

The Smart Agriculture Monitoring System is a comprehensive IoT-based solution designed to modernize farming practices through real-time environmental monitoring, data analytics, and automated decision-making. By integrating various sensors with AWS cloud services, the system provides farmers with actionable insights to optimize resource usage, improve crop yield, and implement sustainable farming practices.

## 🌟 Key Features

- **Real-time Data Collection**
  - Soil moisture and pH monitoring
  - Temperature and humidity tracking
  - Light intensity and rainfall measurement
  - Custom sensor integration capability

- **Cloud-Based Data Processing**
  - Automatic data ingestion via AWS IoT Core
  - Serverless processing with AWS Lambda
  - Time-series data storage in DynamoDB
  - Real-time alerts and notifications

- **Advanced Analytics & Visualization**
  - Historical trend analysis
  - Predictive crop health modeling
  - Resource optimization recommendations
  - Mobile and web dashboard interfaces

- **Automated Farm Management**
  - Smart irrigation control
  - Precision fertilizer application
  - Automated pest and disease detection
  - Weather-based scheduling

- **Infrastructure as Code**
  - Complete AWS infrastructure defined with Terraform
  - Repeatable, version-controlled deployments
  - Environment-specific configurations
  - CI/CD pipeline integration

## 🔧 System Architecture

The Smart Agriculture Monitoring System follows a modern, serverless architecture built on AWS:

```
┌───────────────────┐         ┌───────────────────┐         ┌───────────────────┐
│                   │         │                   │         │                   │
│   Field Sensors   │         │   AWS IoT Core    │         │  Lambda Functions │
│   ───────────     │         │   ───────────     │         │   ───────────     │
│                   │         │                   │         │                   │
│   - Soil Sensors  │         │  - Message Broker │         │  - Data Processing│
│   - Climate Nodes │ ───────►│  - Device Registry│ ───────►│  - Alert Generation│
│   - Water Monitors│         │  - Rules Engine   │         │  - Analytics      │
│   - Camera Systems│         │  - Security       │         │  - API Backend    │
│                   │         │                   │         │                   │
└───────────────────┘         └───────────────────┘         └─────────┬─────────┘
                                                                      │
                                                                      │
                                                                      ▼
┌───────────────────┐         ┌───────────────────┐         ┌───────────────────┐
│                   │         │                   │         │                   │
│    User Interfaces│         │  Data Visualization│◄────────│    Data Storage   │
│    ───────────    │         │    ───────────    │         │    ───────────    │
│                   │         │                   │         │                   │
│   - Web Dashboard │◄────────│  - Real-time Charts│         │  - DynamoDB Tables│
│   - Mobile App    │         │  - Historical Trends│        │  - S3 Data Lake   │
│   - Alerts & Notif│         │  - Heatmaps       │         │  - CloudWatch Logs│
│   - Admin Console │         │  - Reports        │         │  - QuickSight     │
│                   │         │                   │         │                   │
└───────────────────┘         └───────────────────┘         └───────────────────┘
```

## 📦 Project Structure

```
├── docs/                         # Documentation files
│   ├── architecture/             # Architecture diagrams and docs
│   ├── images/                   # Images and graphics
│   └── guides/                   # User and developer guides
├── infrastructure/               # Terraform infrastructure as code
│   ├── modules/                  # Reusable Terraform modules
│   │   ├── iot/                  # IoT Core resources
│   │   ├── lambda/               # Lambda functions
│   │   ├── dynamodb/             # Database resources
│   │   ├── api/                  # API Gateway resources
│   │   └── monitoring/           # CloudWatch resources
│   ├── environments/             # Environment-specific configurations
│   │   ├── dev/                  # Development environment
│   │   ├── staging/              # Staging environment
│   │   └── prod/                 # Production environment
│   └── scripts/                  # Deployment and utility scripts
├── src/                          # Application source code
│   ├── lambda/                   # Lambda function code
│   │   ├── data-processor/       # Data processing function
│   │   ├── alerts-service/       # Alerts and notifications function
│   │   ├── device-manager/       # Device management function
│   │   └── analytics-engine/     # Analytics and ML function
│   ├── iot/                      # IoT related code
│   │   ├── rules/                # IoT Core rules
│   │   └── device-scripts/       # Device-side scripts
│   └── web/                      # Web dashboard application
│       ├── frontend/             # Frontend code (React)
│       └── backend/              # Backend API code
├── firmware/                     # Sensor node firmware
│   ├── soil-moisture-sensor/     # Soil moisture sensor firmware
│   ├── climate-station/          # Climate monitoring station firmware
│   ├── irrigation-controller/    # Irrigation controller firmware
│   └── common/                   # Common firmware libraries
├── tests/                        # Test code
│   ├── unit/                     # Unit tests
│   ├── integration/              # Integration tests
│   └── simulation/               # Sensor data simulators
├── .github/                      # GitHub actions
│   └── workflows/                # CI/CD workflows
├── .gitignore                    # Git ignore file
├── README.md                     # This file
├── LICENSE                       # License file
└── package.json                  # Project dependencies
```

## 🚀 Getting Started

### Prerequisites

- [AWS Account](https://aws.amazon.com/)
- [Terraform](https://www.terraform.io/downloads.html) (v1.0.0+)
- [AWS CLI](https://aws.amazon.com/cli/)
- [Node.js](https://nodejs.org/) (v14.0.0+)
- [Python](https://www.python.org/) (v3.8+)
- [Arduino IDE](https://www.arduino.cc/en/software) (for firmware development)

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/smart-agriculture-monitoring-system.git
   cd smart-agriculture-monitoring-system
   ```

2. **Configure AWS credentials**
   ```bash
   aws configure
   ```

3. **Initialize Terraform**
   ```bash
   cd infrastructure/environments/dev
   terraform init
   ```

4. **Deploy the infrastructure**
   ```bash
   terraform apply
   ```

5. **Install dependencies and start the web dashboard**
   ```bash
   cd ../../../src/web/frontend
   npm install
   npm start
   ```

### Deploying With CI/CD

The repository includes GitHub Actions workflows for continuous integration and deployment:

1. Push changes to the `develop` branch to deploy to the development environment
2. Create a pull request to the `staging` branch to deploy to the staging environment
3. Merge to the `main` branch to deploy to production

## 📊 IoT Sensor Configuration

### Supported Sensor Types

- **Soil Sensors**
  - Moisture content (volumetric water content)
  - Temperature
  - pH level
  - Electrical conductivity
  - Nutrient levels (NPK)

- **Climate Sensors**
  - Air temperature
  - Relative humidity
  - Barometric pressure
  - Light intensity
  - Wind speed and direction
  - Rainfall

- **Water Management Sensors**
  - Flow rate
  - Water level
  - Water quality (pH, turbidity, dissolved oxygen)

### Sensor Registration

To register a new IoT sensor device:

1. Navigate to the administration dashboard
2. Select "Add Device" and choose the sensor type
3. Follow the step-by-step wizard to configure and provision the device
4. Download the generated certificates and configuration
5. Flash the firmware and configuration to your device

## 🌐 AWS Services Utilized

| Service | Purpose |
|---------|---------|
| **AWS IoT Core** | Secure device connectivity, message routing, and device management |
| **AWS Lambda** | Serverless compute for data processing, analytics, and API functionality |
| **Amazon DynamoDB** | Scalable NoSQL database for sensor data and device state storage |
| **Amazon S3** | Object storage for firmware updates, images, and historical data archiving |
| **Amazon CloudWatch** | Monitoring, logging, and alerting for system health and sensor thresholds |
| **AWS IoT Analytics** | Advanced analytics and machine learning on IoT data |
| **Amazon API Gateway** | RESTful API endpoints for web and mobile applications |
| **Amazon Cognito** | User authentication and authorization |
| **AWS SNS** | Notification delivery to users and administrators |
| **AWS IoT SiteWise** | Industrial equipment data collection and organization |

## 📈 Data Analytics Capabilities

The Smart Agriculture Monitoring System provides several analytical capabilities:

- **Historical Trend Analysis**
  - Track changes in soil and climate conditions over time
  - Identify seasonal patterns and correlations
  - Export reports for compliance and documentation

- **Predictive Modeling**
  - Crop water requirement forecasting
  - Disease risk prediction based on environmental factors
  - Yield estimation based on historical and current data

- **Anomaly Detection**
  - Identify unusual soil or climate conditions
  - Early warning for potential equipment failures
  - Detect pest or disease outbreaks

- **Resource Optimization**
  - Irrigation scheduling recommendations
  - Fertilizer application optimization
  - Energy usage monitoring and reduction

## 💼 Use Cases

### Precision Irrigation

The system monitors soil moisture levels in real-time and combines this data with weather forecasts to create optimal irrigation schedules. This minimizes water waste while ensuring crops receive adequate hydration.

### Disease Prevention

By monitoring environmental conditions that promote disease (temperature, humidity, leaf wetness), the system can alert farmers to high-risk periods and recommend preventative measures before crop damage occurs.

### Remote Monitoring

Farmers can access real-time and historical data from anywhere via web and mobile interfaces, enabling informed decision-making without requiring physical presence in the field.

### Resource Management

The system tracks usage of water, fertilizer, and energy, providing insights for optimization and sustainability improvements while reducing operational costs.

## 🛠️ Terraform Infrastructure

This project uses Terraform to provision and manage all AWS resources. Key aspects include:

- **Modular Architecture**: Reusable Terraform modules for each component
- **Environment Separation**: Distinct configurations for development, staging, and production
- **State Management**: Remote state storage in S3 with locking via DynamoDB
- **Secret Management**: Secure handling of sensitive data via AWS Secrets Manager
- **Least Privilege**: IAM policies following principle of least privilege

To customize the deployment:

1. Edit the `terraform.tfvars` file in your target environment directory
2. Run `terraform plan` to review changes
3. Apply changes with `terraform apply`

## 🤝 Contributing

We welcome contributions to the Smart Agriculture Monitoring System! Please see our [Contributing Guide](CONTRIBUTING.md) for details on how to submit changes.

## 📋 Roadmap

- **Q3 2025**: Integration with agricultural machinery via CANbus
- **Q4 2025**: Machine learning models for crop disease identification
- **Q1 2026**: Drone integration for aerial field surveys
- **Q2 2026**: Blockchain-based supply chain traceability
- **Q3 2026**: Multi-tenant SaaS offering for agricultural cooperatives

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

For questions or support, please contact agricultural-tech@example.com or open an issue in this repository.

---

<div align="center">
  <p>Building a sustainable future for agriculture, one data point at a time.</p>
</div>