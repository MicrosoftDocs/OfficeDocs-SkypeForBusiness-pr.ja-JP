---
title: TeamsとSkype相互運用性
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
description: 組織内のユーザーとコンシューマー (コンシューマー) Teamsユーザー間の相互運用Skypeについて説明します。
localization_priority: Normal
ms.openlocfilehash: 3cef040ac9c4ff399b0a663ae25b29f070eb5300
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235182"
---
# <a name="teams-and-skype-interoperability"></a>TeamsとSkype相互運用性

この記事では、アプリケーションとアプリケーション (コンシューマー) の間の相互運用Microsoft Teams Skypeについて説明します。 ユーザーとTeamsユーザーがSkype通話や適用される管理者コントロールを通じて通信する方法について学習します。

Teams内のユーザーは、メール アドレスを使用してチャットSkype通話を行うことができます。その逆も可能です。

- Teamsユーザーは、1 対 1 のテキスト専用会話または音声/ビデオ通話を検索して開始Skypeできます。
- Skypeユーザーは、1 対 1 のテキスト専用会話または音声/ビデオ通話を検索して開始Teamsできます。

これらの機能は、デスクトップ、Web、モバイル (Android および iOS) クライアントで、Teams と Skype。 最適なエクスペリエンスを実現するには、バージョン 8.58 以降Skypeを使用することをお勧めします。

> [!NOTE]
> このTeamsと Skypeの相互運用機能は、GCC、GCC High、DOD のデプロイ、またはプライベート クラウド環境では使用できません。

## <a name="chat-and-calling-experience"></a>チャットと通話のエクスペリエンス

チャットと通話エクスペリエンスの概要を次に示します。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teamsユーザーがチャットを開始したり、他のユーザーと通話Skypeする

Teamsユーザーは、新しいチャットSkype検索バーにメール アドレスを入力して、ユーザーを検索できます。  次Teamsユーザーは、検索結果Skypeユーザーを選択して、チャットを開始したり、チャットを呼び出したりすることができます。

ユーザー Skype検索結果に表示しない場合があります。 この場合、ユーザーは Teams の検索結果に表示Teamsユーザーが検索できない場合があります。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skypeユーザーがチャットを開始するか、他のユーザーと通話Teamsする

Skypeユーザーは、自分のメール アドレスを使用して、Teamsを検索し、チャットを開始できます。 ユーザー Teams、Skype ユーザーから新しいメッセージを受け取り、返信する前に最初にメッセージを承諾する必要があるという通知を受け取ります。

- ユーザーが [Teams] を選択した場合、会話は受け入れ、両方のユーザーがチャットし、互いに通話できます。
- ユーザーが Teams を選択した場合、会話はブロックされ、そのユーザーからの後続のメッセージと呼び出Skypeブロックされます。
- ユーザーが [Teams メッセージの表示] を選択すると、メッセージは Teams に表示され、ユーザーは会話を受け入れるかブロックするか判断できます。

> [!NOTE]
> Skype for Business から Teams にアップグレードし、ユーザーが Teams のみモードの場合は、Skype ユーザーから Teams ユーザーへのチャットと通話が Teams に配信されます。 ユーザーが諸島モードの場合、チャットや通話は、SkypeユーザーからTeamsに配信Skype for Business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teamsユーザーをブロックまたはブロック解除Skypeする

Teamsユーザーが Skype ユーザーからの最初の会話要求を受け入れるかブロックした後は、いつでもそのユーザーをブロックまたはブロック解除できます。 この操作は、会話内で行う場合も、会話のプライバシー設定で行Teams。 Skypeユーザーは、ブロックされているのを知りません。

ブロックSkype他のユーザーと、Teams ユーザーがブロックした公衆交換電話網 (PSTN) 電話番号と共に、Teams のユーザーのブロックされた連絡先リストに一覧表示されます。

## <a name="limitations"></a>制限事項

- 会話はテキスト専用です。 つまり、リッチな書式設定、@mentions、絵文字、その他のチャット機能は、ネイティブのチャット エクスペリエンスで利用Teams[はありません](native-chat-for-external-users.md)。
- 会話は 1 対 1 のみです。 グループ チャットはサポートされていません。
- TeamsユーザーとSkypeユーザーが互いにプレゼンスを表示できない。
- ユーザー ID Skype電話番号を使用してSkypeユーザーを検索する機能はサポートされていません。
- Skypeユーザーは、別のユーザーの番号、代理人の番号、または公衆交換電話網 (PSTN) 番号への転送を設定した Teams ユーザーに通話を発信できない。  ボイスメールだけがサポートされます。
- 相互運用のエスカレーション、グループ通話、会議はサポートされていません。
- 代理人がユーザーに代わってSkypeユーザーを呼び出Teamsはサポートされていません。
- チャットでの画面共有はサポートされていません。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>ユーザーがユーザー Teams通信できるかどうかをSkypeする

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 既定では、この機能は新しいテナントに対して有効になっています。 ただし、ドメインでまだ使用できない場合は、次の DNS SRV レコードを IT 管理者が構成する必要があります (_sipfederationtls.contoso.com など)。  

**サービス**: sipfederationtls<br/>
**プロトコル**: TCP<br/>
**優先度**: 100<br/>
**重** み: 1<br/>
**ポート**: 5061<br/>
**ターゲット**: sipfed.online.lync.com

Skype for Business から Teams にアップグレードした場合、Skype for Business 管理センターで構成した外部通信設定は、Teams に移行されます。

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで

管理センター Microsoft Teams、組織全体の設定の[外部アクセス] に移動し、[ユーザーは他のユーザーと通信Skype  >  **します**。 この設定と他の外部アクセス設定を構成する方法の詳細なガイダンスについては、「外部アクセスの管理」を参照[Teams。](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>PowerShell の使用

以下の操作を行います。 
1. [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)コマンドレットを パラメーターと共に使用して、Teamsユーザーと通信できるかどうか ```EnablePublicCloudAccess``` Skypeします。 パラメーターを に設定すると ```true``` 、ユーザー Teamsユーザーと通信Skypeできます。 パラメーターを使用して ```EnablePublicCloudAudioVideoAccess``` 、音声/ビデオ通話を有効/無効にできます。

2. [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)コマンドレットを パラメーター に設定して、Teamsユーザーと通信Skype ```Provider``` ```"WindowsLive"``` します。

## <a name="related-topics"></a>関連項目

- [Teams で外部アクセスを管理する](manage-external-access.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
