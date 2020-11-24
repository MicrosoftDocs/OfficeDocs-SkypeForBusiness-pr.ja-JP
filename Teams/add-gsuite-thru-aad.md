---
title: Google Workspace 用 Microsoft Teams 会議のアドオンを設定する
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
description: Google Workspace 用の Microsoft Teams 会議アドオンのセットアップ方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387296"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace 用 Microsoft Teams 会議のアドオンを設定する

Microsoft Teams 会議アドオンを使用すると、Google カレンダーのユーザーは、Google Workspace から直接 Microsoft Teams 会議にスケジュールを設定して参加することができます。 ユーザーは、ビデオ通話、電話会議、画面共有、会議チャット、デジタルホワイトボードなどの Teams 会議機能にアクセスできます。 連絡を取り合うことで、仕事、学校、または生活の間でより多くのことを同時に行うことができます。

テナントのユーザーがアプリにアクセスできるようにするには、Google Workspace 用の Microsoft Teams 会議アドオンが Teams 管理者によって有効になっている必要があります。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Azure ポータルで Google Workspace の Microsoft Teams 会議のアドオンを有効または無効にする

テナント管理者は、Azure ポータルを使用して、組織の管理者アカウントから Google Workspace 用の Microsoft Teams 会議アドオンを有効または無効にすることができます。

アドオンは既定で有効になっています。

1. Azure ポータルにサインインします。

2. [**エンタープライズアプリケーション**  >  **すべてのアプリケーション**] を選択します。

3. **Google Workspace 用 Microsoft Teams 会議アドオン** を検索します。

   ![すべてのアプリケーションが表示された Azure portal](media/aad-add-google-workspace.png)

4. [ **はい]** を選びます。

   ![Google workspace のプロパティが表示された Azure ポータル](media/google-workspace-properties.png)

5. 省略アドオンを無効にするには、手順4で [**はい]** ではなく、[**いいえ**] を選びます。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell を使用して Google Workspace 用 Microsoft Teams 会議のアドオンを無効にする

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

詳細については、「 [Azure PowerShell で azure サービスプリンシパルを作成](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)する」を参照してください。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace 用 Microsoft Teams 会議アドオンを削除する

手順については、Google のドキュメントを参照して [Google Workspace Marketplace アプリを削除](https://support.google.com/a/answer/6216211?hl=en) してください。
