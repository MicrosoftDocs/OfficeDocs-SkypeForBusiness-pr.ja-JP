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
description: hyrid アプリケーション エンドポイントを移動してから、オンプレミス環境Skype for Business使用を停止します。
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684384"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>オンプレミス環境を使用停止する前にハイブリッド アプリケーション エンドポイントを移動する

この記事では、オンプレミスのアプリケーション 環境を使用停止する前に、必要なハイブリッド アプリケーション エンドポイントを Microsoft クラウドに移動するSkype for Business説明します。 これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。

- 手順 1. [必要なすべてのユーザーをオンプレミスからオンラインに移動する](decommission-move-on-prem-users.md)

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- **手順 3.ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します。** (この記事)

- 手順 4. [オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>必要なすべてのハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する

これらのエンドポイントをオンラインに移動する前に、エンドポイントで使用されるすべての sip ドメインの Microsoft 365 をポイントする DNS レコードを更新している必要があります。 DNS レコードがオンプレミスを指している場合、オンライン リソース アカウントを作成することはできません。 詳細については、「ハイブリッド構成を [無効にする」を参照してください](cloud-consolidation-disabling-hybrid.md)。

1. PowerShell コマンドで次のオンプレミスアプリケーションを実行して、オンプレミスのハイブリッド アプリケーション エンドポイントSkype for Business Serverエクスポートします。

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 既存の[オンプレミスハイブリッド](/microsoftteams/manage-resource-accounts)アプリケーション エンドポイントMicrosoft 365置き換える新しいリソース アカウントを作成し、ライセンスします。

3. 新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。

4. PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号Skype for Business Server削除します。

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。オンライン PowerShell で次のコマンドSkype for Businessします。

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

6. 手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。 電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](/microsoftteams/manage-resource-accounts#assign-a-service-number)。

7. PowerShell コマンドで次のオンプレミス エンドポイントを実行して、オンプレミスSkype for Business Server削除します。

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
これで、オンプレミスの展開[を削除するSkype for Business準備ができました](decommission-remove-on-prem.md)。

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

- [必要なすべてのユーザーをオンプレミスからオンラインに移動する](decommission-move-on-prem-users.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [オンプレミスの Skype for Business の展開を削除する](decommission-remove-on-prem.md)




