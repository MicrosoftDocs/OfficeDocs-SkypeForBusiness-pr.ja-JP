---
title: オンプレミス環境の使用停止時に DNS エントリを管理する
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
description: オンプレミス環境を使用停止する際に DNS エントリを管理するSkype for Business手順。
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458996"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>DNS エントリを更新して、組織がすべてのユーザーのみTeamsする

以前にオンプレミスの展開が Skype for Business Server または Lync Server に存在していた組織には、オンプレミスの展開を指す DNS エントリSkype for Businessがあります。 これらのレコードは、組織にオンプレミスのユーザーが含まれる場合Skype for Businessです。 ただし、組織にオンプレミスのユーザーまたは Lync Server ユーザー Skype for Businessがなくなったら、これらのレコードは不要になります。 実際、オンプレミスから Teams への移行を完了する一環として、これらのレコードを更新して、Microsoft 365または削除する必要があります。 Microsoft は、この手順を実行できません。

TeamsOnly をテナント全体に付与しようとすると、Teamsは DNS をチェックして、組織にこれらの DNS レコードが存在するかどうかを確認します。 レコードが見つかり、Microsoft 365 以外を指している場合は、テナント共存モードを TeamsOnly に変更しようとすると、設計上失敗します。 この設計は、オンプレミスユーザーを持つハイブリッド組織が、誤って TeamsOnly モードをテナントに適用するのを防ぐためです。これは、オンプレミスの Skype for Business ユーザー (Teams または Skype for Business を使用するかどうか) のフェデレーションを壊す可能性があります。

さらに、これらのレコードを更新して、テナント全体に TeamsOnly を付与する必要があります。

> [!Note] 
> まれに、組織の DNS をオンプレミスのポイントから Microsoft 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する可能性があります。
>
> - 以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。 この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。
> 
> - sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。 この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。 このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。
>
> フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。

## <a name="how-to-identify-stale-dns-records"></a>古い DNS レコードを識別する方法

組織がすべての Teams のみになるのを妨げる DNS レコードを識別するには、Teams 管理センターを使用して共存モードを TeamsOnly に変更できます。 [アップグレード]**の [組織全体の**  ->  **設定Teams移動します**。 組織が [のみ] になTeams DNS レコードは、エラー メッセージに含まれます。  DNS レコードが見つからない場合、組織の共存モードは TeamsOnly に変更されます。 

## <a name="how-to-remove-stale-dns-records"></a>古い DNS レコードを削除する方法

組織にオンプレミスのユーザーまたは Lync Server Skype for Business Serverが存在しない場合は、次の操作を行う必要があります。

- DNS Skype for Businessを更新して、(オンプレミスMicrosoft 365ではなく) DNS レコードをポイントします。

- SIP Skype for Business使用されなくなった場合は、DNS レコードを削除します。 

次のレコードを見つける各ドメインで、次のように更新します。

| レコードの種類 | 名前 | TTL | 優先度 | 太さ | ポート | Value |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  該当なし |   該当なし |   該当なし |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    該当なし |   該当なし  | 該当なし |    sipdir.online.lync.com |
|||||||




