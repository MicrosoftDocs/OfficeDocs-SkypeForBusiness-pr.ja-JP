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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: オンプレミスのSkype for Business環境の使用停止時に DNS エントリを管理する方法について説明します。
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671883"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>組織がすべてのTeamsのみ可能にするように DNS エントリを更新する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Serverまたは Lync Server のオンプレミス展開を以前に行っていた組織には、オンプレミスのSkype for Business展開を指す DNS エントリが引き続き存在する可能性があります。 これらのレコードは、組織にオンプレミスのSkype for Businessユーザーが含まれている場合に必要です。 ただし、組織にオンプレミスのSkype for Businessユーザーや Lync Server ユーザーが存在しなくなったら、これらの元のレコードはオンプレミスの展開では必要なくなり、オンプレミスから Teams への移行の一環として **、これらの DNS エントリを更新してMicrosoft 365を指すように更新する必要があります (場合によっては削除される場合があります**)。 *Microsoft は、お客様に代わってこれらの DNS レコードを更新することはできません。*

TeamsOnly をテナント全体に付与しようとすると、Teamsは DNS を確認して、組織の各Microsoft 365確認済みドメインに次に示す DNS レコードのいずれかが存在するかどうかを確認します。 レコードが見つかり、Microsoft 365以外のレコードを指している場合、テナント共存モードを TeamsOnly に変更しようとすると、設計上失敗します。 これにより、オンプレミス ユーザーを持つハイブリッド組織が誤って TeamsOnly モードをテナントに適用できないようにします。そうすると、組織内のすべてのオンプレミス Skype for Business ユーザーのフェデレーションが解除されるため (TeamsまたはSkype for Businessを使用するかどうか)。

## <a name="how-to-identify-stale-dns-records"></a>古い DNS レコードを識別する方法

組織がすべてのTeamsのみになるのを防ぐ DNS レコードを特定するには、Teams管理センターを使用して共存モードを TeamsOnly に変更できます。 **Teams** >  **Teamsアップグレード設定** に移動します。 組織がTeamsのみになるのを防ぐ DNS レコードは、エラー メッセージに含まれます。  DNS レコードが見つからない場合、組織の共存モードは TeamsOnly に変更されます。

または、次に示すように、powerShell Teamsを使用して同じ操作を行うこともできます。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>更新する DNS レコード

組織でオンプレミスのSkype for Business Serverまたは Lync Server でホストされているユーザーがなくなった場合は、次の操作を行う必要があります。

- 次のSkype for Business DNS レコードの一覧を更新して、(オンプレミスのデプロイではなく) Microsoft 365をポイントします。 複数の SIP ドメインがある場合は、Microsoft 365検証済みドメインである SIP ドメインごとにこれを行う必要があります。

- SIP ドメインが使用されなくなった場合は、Skype for Business DNS レコードを削除します。

次のいずれかのレコードが見つかる各ドメインで、次のように更新します。

|レコードの種類|名前|TTL|優先度|太さ|ポート|Value|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|該当なし|該当なし|該当なし|webdir.online.lync.com|
|CNAME|sip|3600|該当なし|該当なし|該当なし|sipdir.online.lync.com|

さらに、meet または dialin (存在する場合) の CNAME レコードを削除できます。 最後に、内部ネットワーク内のSkype for Businessのすべての DNS レコードを削除する必要があります。

> [!NOTE]
> まれに、DNS をオンプレミスから組織のMicrosoft 365に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが機能しなくなる可能性があります。
>
> - 以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれます) を使用しているすべてのフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。 このレガシ フェデレーション モデルは DNS SRV レコードに基づいていないため、組織がクラウドに移行すると、このような構成は古くなります。
>
> - sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。<span>com では、構成を更新して有効にする必要があります。 この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとのフェデレーションを行ったことがない場合にのみ可能です。 このような場合、これらの組織とのフェデレーションは、ホスティング プロバイダーを有効にするまで機能しません。
>
> フェデレーション パートナーのいずれかがダイレクト フェデレーションを使用しているか、オンラインまたはハイブリッド組織とフェデレーションしていない可能性がある場合は、クラウドへの移行を完了する準備をするときに、これについてのコミュニケーションを送信することをお勧めします。
