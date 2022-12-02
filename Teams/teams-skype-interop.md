---
title: Teams と Skype の相互運用性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内の Teams ユーザーと Skype (コンシューマー) ユーザー間の相互運用性機能について説明します。
ms.localizationpriority: medium
ms.openlocfilehash: 5cbb4bdf492de67131c75c97685317ef8cae866c
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242321"
---
# <a name="teams-and-skype-interoperability"></a>Teams と Skype の相互運用性

この記事では、Microsoft Teams と Skype (コンシューマー) 間の相互運用性機能の概要について説明します。 Teams ユーザーと Skype ユーザーが、チャットや通話、および適用される管理者コントロールを介して通信する方法について説明します。

組織内の Teams ユーザーは、メール アドレスを使用して Skype ユーザーとチャットしたり、Skype ユーザーに電話をかけることができます。その逆も同様です。

- Teams ユーザーは、1 対 1 のテキストのみの会話または Skype ユーザーとの音声/ビデオ通話を検索して開始できます。
- Skype ユーザーは、Teams ユーザーとの 1 対 1 のテキストのみの会話またはオーディオ/ビデオ通話を検索して開始できます。

これらの機能は、Teams と Skype の両方のデスクトップ、Web、モバイル (Android および iOS) クライアントで使用できます。 最適なエクスペリエンスを得るには、Skype バージョン 8.58 以降をお勧めします。

> [!NOTE]
> この記事で説明する Teams と Skype 相互運用機能は、GCC、GCC High、または DOD の展開、またはプライベート クラウド環境では使用できません。

## <a name="chat-and-calling-experience"></a>チャットと通話のエクスペリエンス

チャットと通話エクスペリエンスの概要を次に示します。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams ユーザーが Skype ユーザーとチャットまたは通話を開始する

Teams ユーザーは、新しいチャットまたは検索バーにメール アドレスを入力することで、Skype ユーザーを検索できます。  その後、Teams ユーザーは検索結果で Skype ユーザーを選択して、チャットを開始したり、ユーザーと通話したりできます。

Skype ユーザーが検索結果に表示しないことを選択する場合があります。 この場合、Teams の検索結果には表示されません。また、Teams ユーザーは検索できません。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype ユーザーが Teams ユーザーとチャットまたは通話を開始する

Skype ユーザーは、メール アドレスを使用して Teams ユーザーを検索してチャットを開始できます。 Teams ユーザーは、Skype ユーザーからの新しいメッセージがあることを通知され、最初にメッセージを受け入れてから返信する必要があります。

- Teams ユーザーが **[同意**] を選択すると、会話が受け入れられ、両方のユーザーがチャットして相互に呼び出すことができます。
- Teams ユーザーが **[ブロック**] を選択した場合、会話はブロックされ、その Skype ユーザーからの後続のメッセージと呼び出しはブロックされます。
- Teams ユーザーが [メッセージの **表示**] を選択すると、メッセージが Teams に表示されます。これにより、ユーザーは会話を受け入れるかブロックするかを決定するのに役立ちます。

> [!NOTE]
> Skype for Businessから Teams にアップグレードし、ユーザーが Teams 専用モードの場合、Skype ユーザーから Teams ユーザーへのチャットと通話は Teams に配信されます。 ユーザーがアイランド モードの場合は、Skype ユーザーから Teams ユーザーへのチャットや通話がSkype for Businessに配信されます。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams ユーザーが Skype ユーザーをブロックまたはブロック解除する

Teams ユーザーは、Skype ユーザーからの最初の会話要求を受け入れるかブロックした後、いつでもそのユーザーをブロックまたはブロック解除できます。 これは、会話または Teams のプライバシー設定で行うことができます。 Skype ユーザーは、自分がブロックされたことを知りません。

ブロックされた Skype ユーザーと、Teams ユーザーがブロックした他のユーザーおよび公衆交換電話網 (PSTN) 電話番号は、Teams のユーザーのブロックされた連絡先リストに一覧表示されます。

## <a name="limitations"></a>制限事項

- 会話はテキスト専用です。 つまり、リッチな書式設定、@mentions、絵文字、または [ネイティブの Teams チャット エクスペリエンス](native-chat-for-external-users.md)で利用できるその他のチャット機能はありません。
- 会話は 1 対 1 のみです。 グループ チャットはサポートされていません。
- Teams ユーザーと Skype ユーザーは、お互いのプレゼンスを確認できません。
- Skype ID または電話番号を使用した Skype ユーザーの検索はサポートされていません。
- Skype ユーザーは、別のユーザーの番号、代理人の番号、または公衆交換電話網 (PSTN) 番号への通話転送を設定した Teams ユーザーを呼び出すことはできません。  ボイスメールのみがサポートされています。
- 相互運用エスカレーション、グループ呼び出し、会議はサポートされていません。
- 代理人が Teams ユーザーの代わりに Skype ユーザーを呼び出す機能はサポートされていません。
- チャットでの画面共有はサポートされていません。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Teams ユーザーが Skype ユーザーと通信できるかどうかを設定する

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 既定では、この機能は新しいテナントに対して有効になっています。 ただし、ドメインでまだ使用できない場合は、IT 管理によって次の DNS SRV レコードを構成する必要があるという前提条件があります (例: _sipfederationtls._tcp.contoso.com)。  

**サービス**: sipfederationtls<br/>
**プロトコル**: TCP<br/>
**優先度**: 100<br/>
**重み**: 1<br/>
**ポート**: 5061<br/>
**ターゲット**: sipfed.online.lync.com

Skype for Businessから Teams にアップグレードした場合、Skype for Business管理センターで構成した外部通信設定が Teams に移行されます。

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで

Microsoft Teams 管理センターで、[**ユーザー** > **の外部アクセス**] に移動し、[**ユーザーは Skype ユーザーと通信できます**] をオンにします。 これと他の外部アクセス設定を構成する方法の詳細なガイダンスについては、「 [Teams で外部アクセスを管理](./manage-external-access.md)する」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

以下の操作を行います。 
1. [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) コマンドレットと パラメーターを```EnablePublicCloudAccess```使用して、Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 パラメーターを に ```true``` 設定すると、Teams ユーザーは Skype ユーザーと通信できるようになります。 パラメーターを ```EnablePublicCloudAudioVideoAccess``` 使用して、オーディオ/ビデオ呼び出しを有効または無効にすることができます。

2. [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) コマンドレットと パラメーターを ```Provider``` に```"WindowsLive"```設定して、Teams ユーザーが Skype ユーザーと通信できるようにします。

## <a name="related-topics"></a>関連項目

- [Teams で外部アクセスを管理する](manage-external-access.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
