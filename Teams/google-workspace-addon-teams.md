---
title: Google Workspace Microsoft Teamsの会議アドオンをセットアップする
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
description: Google Workspace の会議アドオンMicrosoft Teamsを設定する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120698"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace Microsoft Teamsの会議アドオンをセットアップする

新しい会議Microsoft Teamsを使用すると、Google カレンダー ユーザーは Google ワークスペースから直接会議Microsoft Teamsスケジュールを設定し、会議に参加できます。 ユーザーは、ビデオTeams会議、画面共有、会議チャット、デジタル ホワイトボードなど、さまざまな会議機能にアクセスできます。 仕事、学校、生活をまたがってより多くの作業を行う場合は、つながって整理します。

テナント Microsoft Teamsユーザーがアプリにアクセスするには、Google ワークスペースの会議アドオンを管理者Teams有効にする必要があります。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Azure portal Microsoft Teams Google Workspace の会議アドオンを有効または無効にする

テナント管理者は、Azure portal を使用して、組織の管理者アカウントから google Workspace の Microsoft Teams 会議アドオンを有効または無効にできます。

アドオンは既定で有効になっています。

1. Azure Portal にサインインします。

2. [**アプリケーションEnterprise すべてのアプリケーション**  >  **] を選択します**。

3. Google Workspace **Microsoft Teamsの会議アドオンを検索します**。

   ![すべてのアプリケーションを表示する Azure Portal](media/aad-add-google-workspace.png)

4. [ **はい] を選択します**。

   ![Google ワークスペースのプロパティを示す Azure Portal](media/google-workspace-properties.png)

5. (省略可能)アドオンを無効にするには、手順 4 で **[は** い] ではなく [ **いいえ** ] を選択します。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell Microsoft Teams Google Workspace の会議アドオンを無効にする

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

詳細については、 を使用した[Azure サービス プリンシパルの作成に関するページAzure PowerShell。](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace Microsoft Teamsの会議アドオンを削除する

手順については、Google のドキュメント [「Google Workspace Marketplace アプリを削除する](https://support.google.com/a/answer/6216211?hl=en) 」を参照してください。