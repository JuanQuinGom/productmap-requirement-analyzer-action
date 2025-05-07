# **product-map-action**
**ProductMap Action** is a GitHub Actions extension designed to automate requirement analysis using 
[ProductMap](https://product-map.ai). This action seamlessly integrates into your GitHub workflow to analyze a repository URL and 
generate corresponding **requirement analysis result**.

Once processed, a markdown file is generated, ensuring that results are accessible directly from the repository.

## **How It Works**

## **Pre-requisites**

Before using this action, ensure that your **GitHub Actions permissions** are properly configured.

### **1. Enable File Read & Write Permissions**
This action needs permission to **read and write files** in your repository when running the workflow. To enable this:

1. Navigate to your **GitHub repository**.
2. Go to **Settings** → **Actions** → **General**.
3. Scroll down to **Workflow permissions**.
4. Select **Read and write permissions**.

### **2. Allow GitHub Actions to Create Pull Requests**
This action automatically creates a **new branch** with the updated `README.md` file and opens a **pull request**. To allow this:

1. Ensure that **GitHub Actions can create pull requests** by granting it access.
2. Add the following permissions to your workflow file:

```yaml
permissions:
  contents: write
  pull-requests: write
```

## **Inputs**

The following inputs must be provided for the action to function correctly within a GitHub workflow:

| Input           | Required | Description |
|----------------|----------|-------------|
| `github_token`  | ✅ Yes  | The GitHub token to access the repository. |
| `user_email`    | ✅ Yes | The email address associated with your **ProductMap** account, used to link the files to your profile. |

Below is an example of how to use the action in your workflow file:
```yaml
...
steps:
  - name: ProductMap Map Generation
    # uses: product-map/product-map-action@main
    uses: product-map/product-map-action@<latest-version>
    with:
      github_token: ${{ secrets.GITHUB_TOKEN }}
      user_email: <your@email.com>
...
```

## **Why Use ProductMap Action?**
| ✅ Benefit | 🌟 Description |
|------------|--------------|
| 🚀 **Automates File Analysis** | No need to manually process files; everything runs within your workflow. |
| 📈 **Tracks Changes Efficiently** | Only modified files are analyzed, optimizing performance. |
| 🌍 **Enhances Collaboration** | Analysis results are publicly available via URLs, making it easy to share insights. |
| 🔄 **Seamless GitHub Integration** | Works natively within GitHub Actions with minimal setup. |

## **Need Help?**
If you encounter any issues or have feature requests, feel free to open an issue in the discord channel!

🔗 Discord channel: [ProductMap Discord](https://discord.gg/zr8wgaaMEK)

