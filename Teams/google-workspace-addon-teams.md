---
title: Google ワークスペースの会議アドオンMicrosoft Teams設定する
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google ワークスペースの会議アドオンMicrosoft Teams設定する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93fecea83a4fb44a19f490af514626a0d17f3ff
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388989"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google ワークスペースの会議アドオンMicrosoft Teams設定する

Microsoft Teams会議アドオンを使用すると、Google 予定表ユーザーは Google ワークスペースから直接Microsoft Teams会議をスケジュールして参加できます。 ユーザーは、ビデオ会議や電話会議、画面共有、会議チャット、デジタルホワイトボードなどのTeams会議機能にアクセスできます。 仕事、学校、生活全体で一緒に作業を行うために、つながりを持ち、整理を続けます。

テナント ユーザーがアプリにアクセスするには、Teams管理者が Google ワークスペースのMicrosoft Teams会議アドオンを有効にする必要があります。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Azure portalで Google ワークスペースの会議アドオンMicrosoft Teams有効または無効にする

テナント管理者は、Azure portalを使用して、組織の管理者アカウントから Google ワークスペースのMicrosoft Teams会議アドオンを有効または無効にすることができます。

アドオンは既定で有効になっています。

1. Azure portalにサインインします。

2. **Enterprise applicationsAll アプリケーション** > **を** 選択します。

3. **Google ワークスペースのMicrosoft Teams会議アドオンを検索します**。

   ![すべてのアプリケーションを表示Azure portal。](media/aad-add-google-workspace.png)

4. **[はい**] を選択します。

   ![google ワークスペースのプロパティを示すAzure portal。](media/google-workspace-properties.png)

5. (省略可能)アドオンを無効にするには、手順 4 で **[はい**] ではなく [**いいえ**] を選択します。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell を使用して Google ワークスペースの会議アドオンMicrosoft Teams無効にする

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
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

詳細については、「[Azure PowerShellを使用した Azure サービス プリンシパルの作成](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)」を参照してください。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google ワークスペースのMicrosoft Teams会議アドオンを削除する

手順については、Google のドキュメント「 [Google ワークスペース Marketplace アプリを削除](https://support.google.com/a/answer/6216211?hl=en) する」を参照してください。

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell を使用して Google ワークスペースのMicrosoft Teams会議アドオンを作成する

Microsoft Teams会議アドオンがテナントに存在しない場合は、PowerShell を使用して作成できます。 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
