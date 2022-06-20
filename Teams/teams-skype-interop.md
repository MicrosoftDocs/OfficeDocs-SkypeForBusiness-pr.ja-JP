---
title: 相互運用性のTeamsとSkype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内のTeams ユーザーとSkype (コンシューマー) ユーザー間の相互運用性機能について説明します。
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167271"
---
# <a name="teams-and-skype-interoperability"></a>相互運用性のTeamsとSkype

この記事では、Microsoft TeamsとSkype (コンシューマー) の間の相互運用性機能の概要について説明します。 ユーザーとSkype ユーザー Teamsチャットや通話、および適用される管理者コントロールを通じて通信する方法について説明します。

組織内のTeamsユーザーは、自分のメール アドレスを使用してSkypeユーザーとチャットしたり、通話したりできます。

- Teamsユーザーは、1 対 1 のテキストのみの会話や、Skype ユーザーとの音声/ビデオ通話を検索して開始できます。
- Skypeユーザーは、1 対 1 のテキストのみの会話や、Teams ユーザーとの音声/ビデオ通話を検索して開始できます。

これらの機能は、デスクトップ、Web、モバイル (AndroidおよびiOS) クライアントで、TeamsとSkypeの両方で使用できます。 最適なエクスペリエンスを得るには、バージョン 8.58 以降Skypeすることをお勧めします。

> [!NOTE]
> この記事で説明する Teams と Skype 相互運用機能は、GCC、GCC High、または DOD の展開、またはプライベート クラウド環境では使用できません。

## <a name="chat-and-calling-experience"></a>チャットと通話のエクスペリエンス

チャットと通話のエクスペリエンスの概要を次に示します。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>TeamsユーザーがSkype ユーザーとチャットまたは通話を開始する

Teamsユーザーは、新しいチャットまたは検索バーにメール アドレスを入力して、Skype ユーザーを検索できます。  その後、Teams ユーザーは検索結果でSkypeユーザーを選択してチャットを開始したり、チャットを開始したり、ユーザーと通話したりできます。

Skypeユーザーは、検索結果に表示しないことを選択できます。 この場合、ユーザーは検索結果にTeamsに表示されません。Teamsユーザーは検索できません。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>SkypeユーザーがTeams ユーザーとチャットまたは通話を開始する

Skypeユーザーは、自分のメール アドレスを使用して、Teams ユーザーとチャットを検索して開始できます。 Teams ユーザーは、Skype ユーザーからの新しいメッセージがあることを通知され、最初にメッセージを受け入れてから返信する必要があります。

- Teams ユーザーが **[同意** する] を選択した場合、会話は受け入れられ、両方のユーザーがチャットして互いに通話できます。
- Teams ユーザーが **[ブロック**] を選択した場合、会話はブロックされ、そのSkype ユーザーからの後続のメッセージと呼び出しはブロックされます。
- Teams ユーザーが [**メッセージの表示**] を選択した場合、メッセージはTeamsに表示されます。これにより、ユーザーは会話を受け入れるかブロックするかを決定できます。

> [!NOTE]
> Skype for BusinessからTeamsにアップグレードし、ユーザーがTeamsのみモードになっている場合、Skype ユーザーからTeams ユーザーへのチャットと通話がTeamsに配信されます。 ユーザーがアイランド モードの場合、Skype ユーザーからTeamsユーザーへのチャットと通話がSkype for Businessに配信されます。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>TeamsユーザーがSkype ユーザーをブロックまたはブロック解除する

Teams ユーザーは、Skype ユーザーからの最初の会話要求を受け入れるかブロックした後、いつでもそのユーザーをブロックまたはブロック解除することができます。 この操作は、会話またはTeamsのプライバシー設定で行うことができます。 Skypeユーザーは、ブロックされたことを知りません。

ブロックSkypeユーザーは、Teams ユーザーがブロックした他のユーザーや公衆交換電話網 (PSTN) の電話番号と共に、Teamsのユーザーのブロックされた連絡先リストに一覧表示されます。

## <a name="limitations"></a>制限事項

- 会話はテキスト専用です。 つまり、ネイティブのTeams チャット エクスペリエンスで利用できる豊富な書式設定、@mentions、絵文字、その他の[チャット](native-chat-for-external-users.md)機能はありません。
- 会話は 1 対 1 のみです。 グループ チャットはサポートされていません。
- Teams ユーザーとSkype ユーザーは互いのプレゼンスを確認できません。
- Skype ID または電話番号を使用したSkypeユーザーの検索はサポートされていません。
- Skypeユーザーは、別のユーザーの番号、代理人の番号、または公衆交換電話網 (PSTN) 番号への通話転送を設定したTeamsユーザーを呼び出すことはできません。  ボイスメールのみがサポートされています。
- 相互運用エスカレーション、グループ通話、会議はサポートされていません。
- 代理人がTeams ユーザーに代わってSkype ユーザーを呼び出す機能はサポートされていません。
- チャットでの画面共有はサポートされていません。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>TeamsユーザーがSkypeユーザーと通信できるかどうかを設定する

管理者は、Microsoft Teams管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内TeamsユーザーがSkype ユーザーと通信できるかどうかを制御します。 既定では、この機能は新しいテナントに対して有効になっています。 ただし、ドメインでまだ使用できない場合は、IT 管理によって次の DNS SRV レコードを構成する必要があるという前提条件があります (例: _sipfederationtls._tcp.contoso.com)。  

**サービス**: sipfederationtls<br/>
**プロトコル**: TCP<br/>
**優先度**: 100<br/>
**重み**: 1<br/>
**ポート**: 5061<br/>
**ターゲット**: sipfed.online.lync.com

Skype for BusinessからTeamsにアップグレードした場合、Skype for Business管理センターで構成した外部通信設定がTeamsに移行されます。

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで

Microsoft Teams管理センターで、[ユーザー **の外部アクセス****]** >  に移動し、[**ユーザーはSkype ユーザーと通信できます**] をオンにします。 これと他の外部アクセス設定を構成する方法の詳細なガイダンスについては、「[Teamsで外部アクセスを管理する](./manage-external-access.md#allow-or-block-domains)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

以下の操作を行います。 
1. [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) コマンドレットをパラメーターと```EnablePublicCloudAccess```共に使用して、Teams ユーザーがSkype ユーザーと通信できるかどうかを制御します。 パラメーターを設定して```true```、Teams ユーザーがSkype ユーザーと通信できるようにします。 このパラメーターを ```EnablePublicCloudAudioVideoAccess``` 使用して、オーディオ/ビデオ通話を有効/無効にすることができます。

2. [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) コマンドレットをパラメーターと```Provider```共に使用して```"WindowsLive"```、Teams ユーザーがSkype ユーザーと通信できるようにします。

## <a name="related-topics"></a>関連項目

- [Teams で外部アクセスを管理する](manage-external-access.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
