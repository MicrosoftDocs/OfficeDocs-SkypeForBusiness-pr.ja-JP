---
title: Skype のビジネス サーバーのダイヤルイン会議をテストします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '概要: は、Skype のビジネス サーバーのダイヤルイン会議をテストする方法を説明します。'
ms.openlocfilehash: 410cbaa9319130dcf4a98c23360362211869e52f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924886"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Skype のビジネス サーバーのダイヤルイン会議をテストします。
 
**の概要:** Skype のビジネス サーバーのダイヤルイン会議をテストする方法について説明します。
  
ダイヤルイン会議構成の最後の確認作業として、どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランやダイヤルイン会議の地域が指定されていないアクセス番号を検索します。 ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることも確認する必要があります。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランの検索

1. コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    このコマンドレットは、どのアクセス番号も使用していないダイヤルイン会議の地域がある、すべてのダイヤル プランを返します。
    
詳細については、 [Get CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)を参照してください。
  
## <a name="find-access-numbers-without-assigned-regions"></a>地域が割り当てられていないアクセス番号の検索

1. コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    このコマンドレットは、地域に関連付けられていないダイヤルイン会議アクセス番号をすべて返します。
    
詳細については、 [Get CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)を参照してください。
  
## <a name="test-webpage-and-access-numbers"></a>Web ページとアクセス番号のテスト

ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。
  
- 簡易 URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。
    
- この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。このスクリプトは、アクセス番号への通話をシミュレートします。このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>特定のプールのアクセス番号をテストするには

1. コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    結果レポートに、コマンドの成否と特定の診断情報が表示されます。 -フラグの詳細についてはどのように多くのアクセス番号が見つかりませんでしたし、それらについての詳細の詳細を提供します。
    
詳細については、[テスト CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)を参照してください。
  

