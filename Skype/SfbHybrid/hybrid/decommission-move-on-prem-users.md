---
title: ユーザーとエンドポイントをクラウドに移動する
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
description: Skype for Business オンプレミス環境を使用停止する前に、ユーザーとエンドポイントを移動します。
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593910"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>オンプレミス環境を使用停止する前に、必要なユーザーとエンドポイントを移動する

この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なユーザーとアプリケーション エンドポイントを Microsoft クラウドに移動する方法について説明します。 これは、オンプレミス環境を使用停止にするための次の手順 1 です。

- **手順 1.必要なすべてのユーザーとアプリケーション エンドポイントをオンプレミスからオンラインに移動します。** (この記事)

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- 手順 3. [オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>必要なすべてのユーザーをオンプレミスからクラウドに移動する

移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。 オンプレミスの管理ツールを使用してユーザーを移動します。 詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。

オンプレミスの Skype for Business Server アカウントを持つユーザーは Teams を使用することができますが、これらのユーザーには Teams の完全な機能はありません。 これらのユーザーは、Skype for Business を引き続き使用している他のユーザー (オンラインでもオンプレミスでも) を相互運用またはフェデレーションすることはできません。 また、これらのユーザーは Teams クライアントで PSTN 通話を受け取る必要もありません。 したがって、これらのユーザーをオンラインに移動する必要があります。 この手順では、Skype for Business Server で作成された連絡先や会議が Teams に移行されます。

オンプレミス展開にユーザーが残っている場合は、Skype for Business Server PowerShell ウィンドウで次のコマンドレットを実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。 不要になったユーザー アカウントの場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> このDisable-CsUserすると、フィルター条件を満たすすべてのユーザーのすべての Skype for Business 属性が削除されます。 先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>オンプレミスのハイブリッド アプリケーション エンドポイントを Microsoft 365 に移動する

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
これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を使用停止する](decommission-on-prem-overview.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [オンプレミスの Skype for Business 展開を削除する](decommission-remove-on-prem.md)




