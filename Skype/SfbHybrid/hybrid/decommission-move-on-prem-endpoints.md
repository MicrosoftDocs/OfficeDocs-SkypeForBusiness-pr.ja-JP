---
title: ハイブリッド アプリケーション エンドポイントをクラウドに移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Skype for Business オンプレミス環境を使用停止する前に、hyrid アプリケーション エンドポイントを移動します。
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656881"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>オンプレミス環境を使用停止する前に、hyrid アプリケーション エンドポイントを移動する

この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なハイブリッド アプリケーション エンドポイントを Microsoft クラウドに移動する方法について説明します。 これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。

- 手順 1. [必要なすべてのユーザーをオンプレミスからオンラインに移動する](decommission-move-on-prem-users.md)

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- **手順 3.ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します。** (この記事)

- 手順 4. [オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>必要なすべてのハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する

これらのエンドポイントをオンラインに移動する前に、エンドポイントで使用されるすべての sip ドメインについて、Microsoft 365 をポイントする DNS レコードを更新している必要があります。 DNS レコードがオンプレミスを指している場合、オンライン リソース アカウントを作成することはできません。 詳細については、「ハイブリッド構成を [無効にする」を参照してください](cloud-consolidation-disabling-hybrid.md)。

1. 次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのハイブリッド アプリケーション エンドポイント設定を取得およびエクスポートします。

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Microsoft 365 で新しい [リソース アカウント](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) を作成してライセンスを取得し、既存のオンプレミスハイブリッド アプリケーション エンドポイントを置き換える。

3. 新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。

4. 次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号を削除します。

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。Skype for Business Online PowerShell で次のコマンドを実行します。

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. 手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。 電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。

7. 次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのエンドポイントを削除します。

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
これで、オンプレミスの [Skype for Business 展開を削除する準備ができました](decommission-remove-on-prem.md)。

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

- [必要なすべてのユーザーをオンプレミスからオンラインに移動する](decommission-move-on-prem-users.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [オンプレミスの Skype for Business の展開を削除する](decommission-remove-on-prem.md)




