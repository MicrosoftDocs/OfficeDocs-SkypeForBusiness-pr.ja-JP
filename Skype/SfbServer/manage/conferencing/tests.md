---
title: 電話でのダイヤルイン会議のSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '概要: 電話会議でダイヤルイン会議をテストするSkype for Business Server。'
ms.openlocfilehash: f02796fff9e610e20751e4e1ca3094d89435a98f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578831"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>電話でのダイヤルイン会議のSkype for Business Server
 
**概要:** ダイヤルイン会議をテストする方法については、Skype for Business Server。
  
ダイヤルイン会議構成の最後の確認作業として、どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランやダイヤルイン会議の地域が指定されていないアクセス番号を検索します。 また、ダイヤルイン会議機能が web ページ設定ダイヤルイン アクセス番号が正しく機能する必要があります。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>アクセス番号で使用されないダイヤルイン会議地域のダイヤル プランを検索する

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    このコマンドレットは、どのアクセス番号も使用していないダイヤルイン会議の地域がある、すべてのダイヤル プランを返します。
    
詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="find-access-numbers-without-assigned-regions"></a>地域が割り当てられていないアクセス番号を検索する

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    このコマンドレットは、地域に関連付けられていないダイヤルイン会議のアクセス番号をすべて返します。
    
詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="test-webpage-and-access-numbers"></a>Web ページとアクセス番号のテスト

ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。
  
- 簡単な URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。
    
- この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。 このスクリプトは、アクセス番号への通話をシミュレートします。 このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>特定のプールのアクセス番号をテストするには

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    結果レポートに、コマンドの成否と特定の診断情報が表示されます。 Verbose フラグは、検出されたアクセス番号の数とアクセス番号に関する詳細な情報を提供します。
    
詳細については [、「Test-CsDialInConferencing」を参照してください](/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。
