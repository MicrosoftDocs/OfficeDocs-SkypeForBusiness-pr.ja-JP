---
title: ハイブリッド接続の構成|2019 Skype for Business Server接続の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ハイブリッド接続を実装する手順は、Skype for Business ServerとTeams。
ms.openlocfilehash: fee7587c641f2fd55cd8b4ac4da72b3944b819a1
ms.sourcegitcommit: 64b9f7297d33a883506893fb68d1ad5202b4df1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59682812"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>デバイスとデバイス間のハイブリッド接続Skype for Business Server構成Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**概要:** このトピックでは、ハイブリッド接続を構成する方法について説明します。Skype for Business ServerとTeams。  ハイブリッド接続を使用すると、オンプレミス のユーザーをクラウド サービスにTeams、ユーザーがクラウド サービスを利用できます。
  
このトピックの手順を実行する前に、「ハイブリッド接続を計画する」を参照Skype for Business Server[と](plan-hybrid-connectivity.md)Teams。
  
次の表に、ハイブリッド接続を構成するためにSkype for Businessタスクの一覧と、関連する記事へのリンクを示します。
  
|手順|説明|
|:-----|:-----|
|Microsoft 365 のテナント アカウントを作成します。   <br/> |詳細については、「Microsoft 365」[を参照Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 環境の準備が完了していることを確認するには、「システムMicrosoft 365」[を参照してください](https://products.office.com/office-system-requirements)。  <br/> ユーザー設定の詳細については、「Microsoft 365[の概要」を参照Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|ドメインを組織に追加Microsoft 365所有権を確認します。  <br/> | ドメインを組織に追加しMicrosoft 365手順に従ってドメインを検証する必要Microsoft 365。 この検証は、ドメインの所有者を確認します。 <br/> ドメインを組織の組織にMicrosoft 365するには、「ドメインを組織に追加する」で説明されている[手順に従](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Microsoft 365。 ハイブリッドになる組織の DNS への影響に関する以下 [のガイダンスを必ず確認してください](#dns-implications-for-on-premises-organizations-that-become-hybrid)。 <br/> |
|Active Directory 同期を設定します。  <br/> |Active Directory の同期により、オンプレミスの Active Directory が Microsoft 365 と継続的に同期され、各ユーザー アカウントとグループの同期バージョンが作成されます。  <br/> <br> **重要:** 組織内のすべての Skype for Business ユーザーの Active Directory アカウントを、ユーザーが Teams に移動されていない場合でも、オンプレミス展開とオンライン展開の間で同期する必要があります。 すべてのユーザーを同期しない場合は、組織内のオンプレミスユーザーとオンライン ユーザー間の通信が期待通りには機能しない場合があります。 詳細については[、「Configure Azure AD Connect ハイブリッド環境」を参照してください](configure-azure-ad-connect.md)。         |
| Skype for Business ハイブリッドを構成します。 | 次の 3 つの基本的な手順があります。 <br><br> 1. オンプレミス環境を構成して、サーバーとフェデレーションMicrosoft 365。 <br> 2. オンプレミス環境を構成して、Microsoft 365を信頼し、共有 SIP アドレス空間を有効Microsoft 365。<br> 3. 組織で共有 SIP アドレス空間Microsoft 365します。 <br><br> また、オンプレミス環境Exchange場合は、オンプレミス環境とオンライン環境の間Exchange OAuth を構成することもできます。 <br> <br>詳細については、「Configure [Skype for Business ハイブリッド」を参照してください](configure-federation-with-skype-for-business-online.md)。
|パイロット ユーザーを移動します。  <br/> |ユーザーの環境を準備して構成する手順を完了したら、Teamsユーザーをオンラインの組織に移動Microsoft 365できます。 詳細については、「ユーザーを[オンプレミスからユーザーに移動する」を参照](move-users-from-on-premises-to-Teams.md)Teams。  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>ハイブリッドになるオンプレミス組織に対する DNS の影響

既定では、テナントは TeamsOnly モードとして作成されます。 管理者は、この構成を変更できません。 ただし、ハイブリッド組織は、オンプレミス ユーザーのフェデレーションを壊す可能性があるため、TeamsOnly モードにする必要があります。 Teamsには、テナント全体の TeamsOnly 構成が新しいハイブリッド テナントに適用されない仕組みと、ハイブリッドになる既存のテナントからテナント全体の TeamsOnly構成が削除される仕組みがあります。 このメカニズムは、以下で説明するように、検証済みの Microsoft 365 ドメインの LyncDiscover DNS レコードの値に基づいて行います (Skype for Business Server オンプレミス展開ではほとんどの場合、そのレコードが含まれるため)。

新しいサブスクリプションMicrosoft 365処理すると、次の処理が行われます。
- ドメインにまだ検証済みのドメインMicrosoft 365、テナントは TeamsOnly モードとして作成されます。 値は、Microsoft でのみ設定できる TeamsUpgradeOverridePolicy を使用して設定されます。 ポリシー値が UpgradeToTeams の場合、TeamsUpgradePolicy の任意の値よりも優先されます。
- Microsoft 365 ドメインが検証済みで、パブリック DNS LyncDiscover レコードが検出されていない場合、またはすべての検出された LyncDiscover レコードが Microsoft 365 (sipfed.online.lync.com、sipfed.online.gov.skypeforbusiness.us など) をポイントしている場合、テナントは TeamsOnly モード (TeamsUpgradeOverridePolicy 経由) として作成されます。
- LyncDiscover レコードが検出された検証済みの Microsoft 365 ドメインが少なくとも 1 つで、そのレコードが Microsoft 365 以外の場所にある場合、テナントはアイランド モードとして作成されます。

既存のMicrosoft 365テナントが再プロビジョニングされる場合 (通常は、検証済みのドメインまたはサブスクリプションの詳細が変更されたため)、次の処理が行われます。
- 1 つ以上の Microsoft 365 検証済みドメインで LyncDiscover レコードが検出され、そのレコードが Microsoft 365 を指していない場合、テナント全体の TeamsOnly モード (TeamsUpgradeOverridePolicy を介して) が削除されます。 テナント モードは、TeamsUpgradePolicy のテナント レベルで指定された値に戻ります。既定ではアイランド モードです。


この自動検出メカニズムにはいくつかの制限があります。
- 組織にパブリック DNS レコードが存在しない場合、TeamsOnly モードは削除されません。Microsoft 365はレコードを検出できません。 組織にパブリック DNS エントリがないオンプレミス Skype for Business Server場合は、Microsoft サポートに問い合わせ、テナントをダウングレードする必要があります。
- 既に Microsoft 365 検証済みのドメインであるドメインにパブリックDNS レコードを追加/更新した場合、この DNS の変更は検出されません。TeamsOnly モードは削除されません。 TeamsOnly モードは、テナントが再プロビジョニングされている場合にのみ削除されます。これは通常、Microsoft 365 検証済みドメインまたはサブスクリプションに変更がある場合に発生します。  
