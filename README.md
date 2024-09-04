# kotoAssignment4
# Get Started with Azure AI Services

In this exercise, you will learn to create an **Azure AI Services** resource in your Azure subscription and use it from a client application. This exercise is designed to help you understand the general pattern of provisioning and working with Azure AI services as a developer, without focusing on any specific service in detail.

## Prerequisites

- Visual Studio Code installed
- An Azure subscription
- Basic knowledge of C# or Python

## Step 1: Clone the Repository

1. Open Visual Studio Code.
2. Use the command palette (SHIFT+CTRL+P) to run a **Git: Clone** command and clone the repository from:
   
   ```
   https://github.com/MicrosoftLearning/mslearn-ai-services
   ```

3. Once cloned, open the folder in Visual Studio Code.

4. If prompted to add required assets to build and debug, select **Not Now**.

5. Navigate to `Labfiles/01-use-azure-ai-services` and choose your preferred language folder (C# or Python).

## Step 2: Provision an Azure AI Services Resource

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Search for *Azure AI services* and create an Azure AI services resource with the following settings:
   - **Subscription**: Your Azure subscription
   - **Resource group**: Choose or create one
   - **Region**: Select an available region
   - **Name**: Provide a unique name
   - **Pricing tier**: Standard S0

3. After deployment, navigate to the **Keys and Endpoint** page of your resource. You will use these values in your application:
   - **Endpoint**: The base URL for your service.
   - **Keys**: Two keys for authentication.
   - **Location**: Region where the resource is hosted (required for some APIs).

## Step 3: Using the Endpoint and Key in the Application

### Configure the Application

1. Locate the configuration file in the **rest-client** folder:
   - **C#**: `appsettings.json`
   - **Python**: `.env`

2. Update the configuration file with your Azure AI Services **endpoint** and **key**:
   
   **C# (`appsettings.json`):**
   ```json
   {
     "AzureAI": {
       "Endpoint": "YOUR_ENDPOINT",
       "Key": "YOUR_KEY"
     }
   }
   ```

   **Python (`.env`):**
   ```
   AZURE_AI_ENDPOINT=YOUR_ENDPOINT
   AZURE_AI_KEY=YOUR_KEY
   ```

3. Save your changes.

### Run the REST Client Application

1. Navigate to the **rest-client** folder in the terminal.
   
2. Run the following commands to execute the application:
   
   **C#**
   ```
   dotnet run
   ```

   **Python**
   ```
   pip install python-dotenv
   python rest-client.py
   ```

3. Test the application by entering text inputs like "Hello", "Bonjour", or "Gracias" to see the detected language.

## Step 4: Using the SDK

1. Navigate to the **sdk-client** folder under your preferred language (C# or Python).
   
2. Install the Text Analytics SDK:
   
   **C#**
   ```
   dotnet add package Azure.AI.TextAnalytics --version 5.3.0
   ```

   **Python**
   ```
   pip install azure-ai-textanalytics==5.3.0
   ```

3. Update the configuration file in the **sdk-client** folder with your Azure AI Services **endpoint** and **key** as described in Step 3.

4. Run the SDK client application using:

   **C#**
   ```
   dotnet run
   ```

   **Python**
   ```
   python sdk-client.py
   ```

5. Test the application with different text inputs to detect languages.

## Step 5: Clean Up Resources

1. To avoid additional costs, delete the Azure resources you created during this lab. You can delete the individual resource or the entire resource group.

## Additional Resources

For further details on Azure AI Services, visit the [Azure AI Services documentation](https://docs.microsoft.com/azure/ai-services/what-are-ai-services).
