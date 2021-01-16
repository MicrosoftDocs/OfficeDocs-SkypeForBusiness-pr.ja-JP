---
title: Google Workspace の Microsoft Teams 会議アドオンをセットアップする
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google Workspace 用に Microsoft Teams 会議アドオンをセットアップする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880878"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="497fa-103">Google Workspace の Microsoft Teams 会議アドオンをセットアップする</span><span class="sxs-lookup"><span data-stu-id="497fa-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="497fa-104">Microsoft Teams 会議アドオンを使用すると、Google カレンダー ユーザーは Google Workspace から直接 Microsoft Teams 会議をスケジュールし、参加することができます。</span><span class="sxs-lookup"><span data-stu-id="497fa-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="497fa-105">ユーザーは、ビデオ会議、電話会議、画面共有、会議チャット、デジタル ホワイトボードなどの Teams 会議機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="497fa-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="497fa-106">仕事、学校、生活の全体で、より多くのことを一緒に行う場合は、接続と整理を行います。</span><span class="sxs-lookup"><span data-stu-id="497fa-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="497fa-107">テナント ユーザーがアプリにアクセスするには、Google Workspace 用の Microsoft Teams 会議アドオンを Teams 管理者が有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="497fa-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="497fa-108">Azure Portal で Google Workspace の Microsoft Teams 会議アドオンを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="497fa-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="497fa-109">テナント管理者は、Azure Portal を使用して、組織の管理者アカウントから Google Workspace の Microsoft Teams 会議アドオンを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="497fa-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="497fa-110">既定では、アドオンは有効になっています。</span><span class="sxs-lookup"><span data-stu-id="497fa-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="497fa-111">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="497fa-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="497fa-112">[エンタープライズ **アプリケーション] の [**  >  **すべてのアプリケーション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="497fa-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="497fa-113">Google **Workspace の Microsoft Teams 会議アドオンを検索します**。</span><span class="sxs-lookup"><span data-stu-id="497fa-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![すべてのアプリケーションを表示する Azure Portal](media/aad-add-google-workspace.png)

4. <span data-ttu-id="497fa-115">[はい **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="497fa-115">Select **Yes**.</span></span>

   ![Google ワークスペースのプロパティを表示する Azure Portal](media/google-workspace-properties.png)

5. <span data-ttu-id="497fa-117">(省略可能)アドオンを無効にするには、手順 4 で [ **は** い] ではなく **[いいえ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="497fa-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="497fa-118">PowerShell を使用して Google Workspace の Microsoft Teams 会議アドオンを無効にする</span><span class="sxs-lookup"><span data-stu-id="497fa-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

<span data-ttu-id="497fa-119">詳細については [、「Azure PowerShell で Azure サービス プリンシパルを作成する」を参照してください](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。</span><span class="sxs-lookup"><span data-stu-id="497fa-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="497fa-120">Google Workspace の Microsoft Teams 会議アドオンを削除する</span><span class="sxs-lookup"><span data-stu-id="497fa-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="497fa-121">手順については、Google のドキュメント [「Google Workspace Marketplace アプリを削除する」](https://support.google.com/a/answer/6216211?hl=en) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="497fa-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
