---
title: チームと Skype の相互運用性
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内の Teams ユーザーと Skype (コンシューマー) ユーザーとの相互運用性機能について説明します。
localization_priority: Normal
ms.openlocfilehash: 9bb38fa33e7ef3692f5946fef4769bb45f782f1a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030973"
---
# <a name="teams-and-skype-interoperability"></a>チームと Skype の相互運用性

この記事では、Microsoft Teams と Skype (コンシューマー) との間の相互運用性機能の概要について説明します。 チームのユーザーと Skype ユーザーが、チャットや通話、および適用される管理コントロールによってコミュニケーションを行う方法について説明します。

組織内の Teams ユーザーは、自分のメールアドレスを使って Skype のユーザーとチャットしたり、その逆に通話したりできます。

- Teams ユーザーは、1対1のテキストのみの会話、または Skype ユーザーとの音声/ビデオ通話を検索して開始することができます。
- Skype ユーザは、1対1のテキストのみの会話、または Teams ユーザとの音声/ビデオ通話を検索して開始することができます。

これらの機能は、Teams と Skype の両方のデスクトップ、web、モバイル (Android および iOS) クライアントで利用できます。 最適なエクスペリエンスを実現するには、Skype バージョン8.58 以降をお勧めします。

> [!NOTE]
> この記事で説明されているチームおよび Skype 相互運用機能は、GCC、GCC 高、または DOD の展開やプライベートクラウド環境では使用できません。

## <a name="chat-and-calling-experience"></a>チャットと通話のエクスペリエンス

チャットと通話のエクスペリエンスの概要を以下に示します。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams ユーザーが Skype ユーザーとのチャットまたは通話を開始する

Teams ユーザーは、新しいチャットまたは検索バーに自分のメールアドレスを入力して、Skype ユーザーを検索することができます。  チームユーザは、検索結果で Skype ユーザを選択して、チャットまたは通話を開始できます。

Skype ユーザは、検索結果に表示されないように選択できます。 この場合、チームの検索結果には表示されず、Teams ユーザーはそれらを見つけることができません。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype ユーザが Teams ユーザとチャットまたは通話を開始

Skype ユーザは、自分のメールアドレスを使って、チームユーザとのチャットを検索して開始することができます。 チームユーザには、Skype ユーザからの新しいメッセージがあることが通知され、最初にメッセージを受信しないと返信できません。

- Teams ユーザーが [ **承諾** ] を選択すると、会話が承諾され、両方のユーザーがチャットして通話を発信できるようになります。
- Teams ユーザーが **ブロック** を選択した場合、会話はブロックされ、その後の Skype ユーザからのメッセージや通話はブロックされます。
- Teams ユーザーが [ **メッセージの表示** ] を選択すると、そのメッセージが teams に表示され、ユーザーはその会話を承認またはブロックするかどうかを決定できます。

> [!NOTE]
> Skype for Business から Teams にアップグレードして、ユーザーが Teams のみモードの場合は、Skype ユーザーから Teams ユーザーへのチャットや通話が Teams に配信されます。 ユーザが諸島モードになっている場合は、Skype ユーザから Teams ユーザへのチャットや通話が Skype for Business に配信されます。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams ユーザーが Skype ユーザーをブロックまたはブロック解除する

チームのユーザーが Skype ユーザーからの最初の会話要求を承諾またはブロックした後は、そのユーザーはいつでもブロックまたはブロック解除することができます。 この操作は、会話または Teams のプライバシー設定で行うことができます。 Skype ユーザは、ブロックされていることを認識できません。

ブロックされた Skype ユーザーと、他のユーザー、および Teams ユーザーがブロックした公衆交換電話網 (PSTN) 電話番号は、チームのユーザーのブロックされた連絡先リストに一覧表示されます。

## <a name="limitations"></a>伴う

- 会話はテキストのみです。 これは、ネイティブな [書式設定]、[@mentions]、[絵文字] などの他のチャット機能がないことを意味します。これは、 [ネイティブのチームチャットエクスペリエンス](native-chat-for-external-users.md)で利用できます。
- 会話は1対1でのみ行うことができます。 グループチャットはサポートされていません。
- Teams ユーザーと Skype ユーザーは、互いのプレゼンスを見ることはできません。
- Skype ID または電話番号を使用して Skype ユーザを検索することはサポートされていません。
- Skype ユーザは、他のユーザの番号、代理人の番号、公衆交換電話網 (PSTN) 番号への通話転送を設定した Teams ユーザとは通話できません。  ボイスメールのみがサポートされています。
- 相互運用エスカレーション、グループ通話、会議はサポートされません。
- Teams ユーザの代理として、代理人が Skype ユーザに通話を発信する機能はサポートされていません。
- チャットでの画面共有はサポートされていません。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>チームユーザーが Skype ユーザーと通信できるかどうかを設定する

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 既定では、新しいテナントではこの機能が有効になっています。 ただし、ドメインでまだ利用できない場合は、次の DNS SRV レコードを IT 管理者が構成する必要があることを前提としています (例 _sipfederationtls. .com)。  

**Service** : sipfederationtls<br/>
**プロトコル** : TCP<br/>
**優先度** : 100<br/>
**重さ** : 1<br/>
**ポート** : 5061<br/>
**Target** : sipfed.online.lync.com

Skype for Business から Teams にアップグレードした場合、Skype for Business 管理センターで構成した外部通信設定が Teams に移行されます。

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで

Microsoft Teams 管理センターで、[ **組織全体の設定** ] の [外部アクセス] に移動し、[  >  **External access****ユーザーが Skype ユーザーと通信できるよう** にする] をオンにします。 このような外部アクセス設定を構成する方法については、「 [Teams で外部アクセスを管理](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)する」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

以下の操作を行います。 
1. パラメーターと共に [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) コマンドレットを使用して、 ```EnablePublicCloudAccess``` Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。 ```true```チームユーザーが Skype ユーザーと通信できるようにパラメーターを設定します。 このパラメーターを使って、 ```EnablePublicCloudAudioVideoAccess``` 音声/ビデオ通話を有効または無効にすることができます。

2. Teams ユーザーが Skype ユーザーと通信できるように、 [set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) コマンドレットを使用してパラメーターセットと一緒に使用し ```Provider``` ```"WindowsLive"``` ます。

## <a name="related-topics"></a>関連項目

- [Teams で外部アクセスを管理する](manage-external-access.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
