---
title: Teams と Skype の相互運用性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内の Teams ユーザーと Skype (コンシューマー) ユーザー間の相互運用性機能について説明します。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093957"
---
# <a name="teams-and-skype-interoperability"></a>Teams と Skype の相互運用性

この記事では、Microsoft Teams と Skype (コンシューマー) 間の相互運用性機能の概要について説明します。 Teams ユーザーと Skype ユーザーがチャットや通話を通じて通信する方法と、適用される管理者コントロールについて学習します。

組織内の Teams ユーザーは、メール アドレスを使用して Skype ユーザーとチャットや通話を行うことができます。その逆も可能です。

- Teams ユーザーは、Skype ユーザーと 1 対 1 のテキストのみ会話または音声/ビデオ通話を検索して開始できます。
- Skype ユーザーは、Teams ユーザーと 1 対 1 のテキストのみ会話または音声/ビデオ通話を検索して開始できます。

これらの機能は、Teams と Skype の両方のデスクトップ、Web、モバイル (Android および iOS) クライアントで使用できます。 最適なエクスペリエンスを得る場合は、Skype バージョン 8.58 以降をお勧めします。

> [!NOTE]
> この記事で説明する Teams と Skype の相互運用機能は、GCC、GCC High、DOD 展開、またはプライベート クラウド環境では利用できません。

## <a name="chat-and-calling-experience"></a>チャットと通話のエクスペリエンス

チャットと通話のエクスペリエンスの概要を示します。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams ユーザーが Skype ユーザーとのチャットまたは通話を開始する

Teams ユーザーは、新しいチャットまたは検索バーに自分のメール アドレスを入力して、Skype ユーザーを検索できます。  Teams ユーザーは、検索結果で Skype ユーザーを選択してチャットを開始したり、通話を開始したりすることができます。

Skype ユーザーが検索結果に表示されない場合があります。 この場合、Teams の検索結果には表示され、Teams のユーザーはそれらを見つけ出せしません。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype ユーザーが Teams ユーザーとのチャットまたは通話を開始する

Skype ユーザーは、自分のメール アドレスを使用して Teams ユーザーを検索してチャットを開始できます。 Teams ユーザーは、Skype ユーザーから新しいメッセージを受け取り、返信する前に最初にメッセージを承諾する必要があるという通知を受け取ります。

- Teams ユーザーが [承諾] **を選** ぶと、会話は承諾され、両方のユーザーが互いにチャットや通話を行える。
- Teams ユーザーが [ブロック] **を選択** すると、会話はブロックされ、その Skype ユーザーからの以降のメッセージと通話はブロックされます。
- Teams ユーザーが [メッセージの表示] を選択すると、メッセージが Teams に表示され、ユーザーが会話を受け入れるかブロックするかの決定に役立ちます。

> [!NOTE]
> Skype for Business から Teams にアップグレードし、ユーザーが Teams のみモードの場合、Skype ユーザーから Teams ユーザーへのチャットと通話は Teams に配信されます。 ユーザーが諸島モードの場合、Skype ユーザーから Teams ユーザーへのチャットと通話は Skype for Business に配信されます。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams ユーザーが Skype ユーザーをブロックまたはブロック解除する

Teams ユーザーは、Skype ユーザーからの最初の会話要求を承諾またはブロックした後、いつでもそのユーザーをブロックまたはブロック解除することができます。 この操作は、会話または Teams のプライバシー設定で行います。 Skype ユーザーは、ブロックされたユーザーを知りません。

ブロックされた Skype ユーザーと、Teams ユーザーがブロックした他のユーザーおよび公衆交換電話網 (PSTN) 電話番号は、Teams のユーザーのブロックされた連絡先リストに一覧表示されます。

## <a name="limitations"></a>制限事項

- 会話はテキスト専用です。 つまり、リッチフォーマット、@mentions、絵文字、またはネイティブ [の Teams](native-chat-for-external-users.md)チャットエクスペリエンスで使用できるその他のチャット機能はありません。
- 会話は 1 対 1 のみです。 グループ チャットはサポートされていません。
- Teams ユーザーと Skype ユーザーは、互いにプレゼンスを表示できない。
- Skype ID または電話番号を使用して Skype ユーザーを検索する機能はサポートされていません。
- Skype ユーザーは、別のユーザーの番号、代理人の番号、または公衆交換電話網 (PSTN) 番号への転送を設定した Teams ユーザーに通話を発信できない。  ボイスメールだけがサポートされます。
- 相互運用のエスカレーション、グループ通話、会議はサポートされません。
- 代理人が Teams ユーザーの代わりに Skype ユーザーを呼び出す機能はサポートされていません。
- チャットでの画面共有はサポートされていません。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Teams ユーザーが Skype ユーザーと通信できるかどうかを設定する

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 既定では、この機能は新しいテナントに対して有効になっています。 ただし、ドメインでまだ使用できない場合は、次の DNS SRV レコードを IT 管理者が構成する必要があります (_sipfederationtls.contoso.com など)。  

**サービス**: sipfederationtls<br/>
**プロトコル**: TCP<br/>
**優先度**: 100<br/>
**太** さ : 1<br/>
**ポート**: 5061<br/>
**ターゲット**: sipfed.online.lync.com

Skype for Business から Teams にアップグレードした場合、Skype for Business 管理センターで構成した外部通信設定が Teams に移行されます。

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで

Microsoft Teams 管理センターで、組織全体の設定の外部アクセスに移動し、ユーザーが Skype ユーザーと通信できる  >  **機能を有効にします**。 この設定と他の外部アクセス設定を構成する方法の詳細なガイダンスについては、「Teams で外部アクセスを管理する」を [参照してください](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>PowerShell の使用

以下の操作を行います。 
1. パラメーターと [共に Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) コマンドレットを使用して、Teams ユーザーが Skype ユーザーと通信できるかどうか ```EnablePublicCloudAccess``` を制御します。 パラメーターを設定すると ```true``` 、Teams ユーザーは Skype ユーザーと通信できます。 パラメーターを使用して ```EnablePublicCloudAudioVideoAccess``` 、音声/ビデオ通話を有効/無効にできます。

2. [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)コマンドレットとパラメーターセットを組み合わせて使用すると、Teams ユーザーは Skype ユーザーと ```Provider``` ```"WindowsLive"``` 通信できます。

## <a name="related-topics"></a>関連項目

- [Teams で外部アクセスを管理する](manage-external-access.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)