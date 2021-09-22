---
title: EDU Microsoft 保護者アプリの管理者セットアップ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU の詳細については、保護者向けアプリの前提条件と PowerShell のセットアップに関する記事を参照してください。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475910"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>親アプリをデプロイするMicrosoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams で保護者アプリを有効にすることで、管理者は簡単なプロセスであり、教師が学生と、テナント内に残っている連絡先と通信し、教師組織全体で拡張するための安全な方法を提供します。

## <a name="requirements"></a>要件

- SDS (School Data Sync) - CSV オプションを使用して、学生に関連付けられている関連する連絡先を SDS にアップロードする必要があります。 詳細については [、「SDS および更新関連](/schooldatasync/set-up-your-sds-flow) の CSV の構成 [」を](/graph/api/relatedcontact-update) 参照してください。
- 管理Teams、クラス所有者がチャットを有効にし、組織によって管理されていないTeams アカウントとのフェデレーション チャット **が必要です**。

フェデレーション チャットをユーザーごとに有効にする必要がある場合は、以下の手順を実行します。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>ユーザーごとにフェデレーション チャットを有効にする

1. PowerShell モジュール プレビュー Microsoft Teams最新バージョンをインストールします。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. 管理者特権を持つ資格情報を使用して、コマンド ウィンドウで を実行します。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. グローバル グループ/ユーザー レベルの構成またはテナント レベルの構成で、オンとオフを切り替えます。

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > この PowerShell を実行する場合、変更が完了するには 1 時間以上かかる場合があります。
    
## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [ユーザーへのポリシーの割り当て](/powershell/module/skype/grant-csexternalaccesspolicy)
