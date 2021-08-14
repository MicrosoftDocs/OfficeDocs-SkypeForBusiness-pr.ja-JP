---
title: ハイブリッドを無効にして Teams のみの移行を完了する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この記事では、クラウド統合の一環としてハイブリッドを無効にするための詳細な手順について説明TeamsおよびSkype for Business。
ms.openlocfilehash: eb7e72644bf5f69a763540c1c256d7aabb5f9f6f474d1d570071f68a4c2584e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330701"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>ハイブリッド構成を無効にして、ハイブリッド構成への移行Teamsのみ 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


この記事では、オンプレミス環境を使用停止する前にハイブリッド構成を無効にするSkype for Business説明します。 これは、オンプレミス環境を使用停止するための次の手順の手順 2 です。

- 手順 1. [必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。

- **手順 2.ハイブリッド構成を無効にします。** (この記事)

- 手順 3. [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します](decommission-move-on-prem-endpoints.md)。

- 手順 4. [オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。

> [!NOTE]
> 手順 2 と手順 3 は、手順 2 と手順 3 の完了の間に既存のハイブリッド アプリケーション エンドポイントを検出できないので、同じメンテナンス ウィンドウで実行する必要があります。


## <a name="summary"></a>要約

すべてのユーザーを Skype for Business オンプレミスから Teams のみ Microsoft 365 にアップグレードした後、オンプレミスの展開をSkype for Businessできます。

オンプレミスの Skype for Business 展開を使用停止し、ハードウェアを削除する前に、ハイブリッドを無効にして、オンプレミス展開と Microsoft 365を論理的に分離する必要があります。 ハイブリッドの無効化は、次の 4 つの手順で構成されます。

1. [DNS レコードを更新して、DNS レコードを参照Microsoft 365。](#update-dns-to-point-to-microsoft-365)

2. [組織の共存モードを [のみ] にTeamsします](#change-the-coexistence-mode-for-your-organization-to-teams-only)。

3. [組織で共有 SIP アドレス空間 ("分割ドメイン" とも呼ばれる) をMicrosoft 365します](#disable-shared-sip-address-space-in-microsoft-365-organization)。

4. [オンプレミスとユーザー間の通信を無効Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

次の手順では、オンプレミスの展開と Skype for Business Serverを論理的にMicrosoft 365、組織が完全にTeamsします。 これらの手順を完了したら、「使用停止後に属性を管理する方法を決定する」で参照されている 2 つの方法のいずれかを使用して、オンプレミスの Skype for Business 展開を使用停止[できます](cloud-consolidation-managing-attributes.md)。

> [!Important] 
> この論理的な分離が完了すると、オンプレミスの Active Directory の msRTCSIP 属性には値が残り、Azure AD Connect を介して Azure AD に同期されます。 オンプレミス環境を使用停止する方法は、これらの属性をそのままにするか、最初にオンプレミスの Active Directory から削除するかによって異なります。 オンプレミスから移行した後にオンプレミスの msRTCSIP 属性をクリアすると、ユーザーのサービスが失われる可能性があります。 2 つの使用停止アプローチの詳細とトレードオフについては、「使用停止後に属性を管理する方法を決定する」 [を参照してください](cloud-consolidation-managing-attributes.md)。

## <a name="update-dns-to-point-to-microsoft-365"></a>DNS を更新して、ユーザーをポイントMicrosoft 365

オンプレミス組織の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミス展開ではなく Microsoft 365 を指す必要があります。 

さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。 最後に、内部ネットワーク内Skype for Business DNS レコードを削除する必要があります。

DNS レコードの更新の詳細については、「UPDATE DNS エントリを使用して組織をすべてのユーザーのみTeams[してください](decommission-manage-dns-entries.md)。

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>組織の共存モードを [共有のみ] にTeamsする

この手順では、組織内のすべての新しいユーザーが常に [ユーザーのみ] Teamsされます。 

テナント モードを Teams のみに変更しようとすると、手順 1 で見つからない可能性のあるオンプレミス DNS レコードが自動的に存在することを確認し、出力でこれらのレコードを識別します。 テナント モードを [Teamsのみ] に変更すると、組織のすべての DNS レコードが更新されるまで成功しません。 

テナント モードを [テナント モード] にTeams PowerShell ウィンドウから次のコマンドTeams実行します。

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

または、Teams 管理センターを使用して、[組織全体の設定] -> "Teams アップグレード" の下で、テナント共存モードを TeamsOnly に変更できます。    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>組織で共有 SIP アドレス空間をMicrosoft 365する
    
共有 SIP アドレス空間を無効にするには、PowerShell ウィンドウから次Teams実行します。

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>オンプレミスとユーザー間の通信を無効Microsoft 365

オンプレミス環境とサーバー間の通信を無効にするにはMicrosoft 365、オンプレミスの PowerShell ウィンドウから次のコマンドを実行します。

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>関連項目

- [クラウドの統合 :TeamsとSkype for Business](cloud-consolidation.md)

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

