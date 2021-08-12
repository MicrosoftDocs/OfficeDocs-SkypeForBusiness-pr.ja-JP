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
ms.openlocfilehash: 0dabf9790b1e579d136fef459308af450e879b110474b2877513855c8e78cf29
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315173"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>DNS エントリを更新して、組織がすべてのユーザーのみTeamsする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

以前にオンプレミスの展開が Skype for Business Server または Lync Server に存在していた組織には、オンプレミスの展開を指す DNS エントリSkype for Businessがあります。 これらのレコードは、組織にオンプレミスのユーザーが含まれる場合Skype for Businessです。 ただし、組織にオンプレミスの Skype for Business または Lync Server ユーザーが存在しなくなった場合、これらの元のレコードはオンプレミス展開では不要になります。これらの **DNS** エントリは、オンプレミスから Teams への移行の一環として Microsoft 365 をポイント (または場合によっては削除) に更新する必要があります。 *Microsoft は、お客様に代わってこれらの DNS レコードを更新することはできません。*

テナント全体に TeamsOnly を付与しようとすると、Teams は DNS をチェックして、以下に示す DNS レコードが組織内の Microsoft 365 検証済みドメインのそれぞれに存在するかどうかを確認します。 レコードが見つかり、Microsoft 365 以外を指している場合は、テナント共存モードを TeamsOnly に変更しようとすると、設計上失敗します。 これにより、オンプレミスユーザーを持つハイブリッド組織が TeamsOnly モードをテナントに誤って適用するのを防ぐのは、組織内のすべてのオンプレミス Skype for Business ユーザー (Teams または Skype for Business を使用するかどうか) のフェデレーションが壊れるためです。


## <a name="how-to-identify-stale-dns-records"></a>古い DNS レコードを識別する方法

組織がすべての Teams のみになるのを妨げる DNS レコードを識別するには、Teams 管理センターを使用して共存モードを TeamsOnly に変更できます。 [アップグレード]**の [組織全体の**  ->  **設定Teams移動します**。 組織が [のみ] になTeams DNS レコードは、エラー メッセージに含まれます。  DNS レコードが見つからない場合、組織の共存モードは TeamsOnly に変更されます。   

または、PowerShell Teamsを使用して、以下に示すように同じ操作を実行できます。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>更新する DNS レコード

組織でオンプレミス または Lync Server でホストされているユーザーが存在しなくなったSkype for Business Server、次の操作を行う必要があります。

- 以下のSkype for Business DNS レコードの一覧を更新して、Microsoft 365展開ではなく、 をポイントします。 複数の SIP ドメインがある場合は、認証済みドメインである SIP ドメインごとにMicrosoft 365必要があります。

- SIP Skype for Business使用されなくなった場合は、DNS レコードを削除します。 

次のレコードを見つける各ドメインで、次のように更新します。

| レコードの種類 | 名前 | TTL | 優先度 | 太さ | ポート | Value |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  該当なし |   該当なし |   該当なし |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    該当なし |   該当なし  | 該当なし |    sipdir.online.lync.com |
|||||||

さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。 最後に、内部ネットワーク内Skype for Business DNS レコードを削除する必要があります。

> [!Note] 
> まれに、組織の DNS をオンプレミスのポイントから Microsoft 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する可能性があります。
>
> - 以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。 この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。
> 
> - sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。 この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。 このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。
>
> フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。
  




