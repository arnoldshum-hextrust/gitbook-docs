# API Key Management

### API Key permissions

Let's understand how does permissions work for API keys.

An API key is simply an extension of how a user can access the Hex Safe v2 platform. The API key inherits the same permissions of the user who created and owns the API key.

The permission of the user depends on the role it's assigned to.

### CSR generation

### API key generation guide

The follow is a guide on generating your API key via the Hex Safe v2 UI.

1. Login to your Hex Safe v2 account.
2. Go to the Settings page.
3. Navigate to the API Key tab.
4. Click "Create API Key". A modal will pop up.
5. Complete the following fields:
   * **Name**: Enter the name you want to give your API key.
   * **Certificate Signing Requests (CSR)**: Copy and paste the content from the CSR file ([_how to generate CSR file?_](./#csr-generation)_)._
   * **Expire after**: Select when you want the api key to active for or set it to never expire.
6. Click "Get API Key" to create your API key.
7. Once the API key is successfully generated, you will see on a success screen. Click "Close" to close the modal.
8. A (new) API key now appears in the API key list. Select the eye icon reveal your API key or the copy icon to copy your API key.

\\
