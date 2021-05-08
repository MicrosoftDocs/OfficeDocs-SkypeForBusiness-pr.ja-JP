---
title: Microsoft Teams アプリのアクセス許可と考慮事項
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理者は、アプリが組織に要求Microsoft Teamsデータとアクセス許可を確認できます。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120859"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams アプリのアクセス許可と考慮事項

Microsoft Teamsは、1 つ以上の機能を、インストール、アップグレード、アンインストールできるアプリ パッケージに集約する方法です。 機能は次のとおりです。

- ボット
- メッセージング拡張機能
- タブ
- コネクタ

アプリはユーザーによって同意され、ポリシーの観点から IT によって管理されます。 ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルは、アプリに含まれる機能のアクセス許可とリスク プロファイルによって定義されます。 そのため、この記事では、機能レベルでのアクセス許可と考慮事項について説明します。

以下に示すアクセス許可 (RECEIVE_MESSAGE や REPLYTO_MESSAGE など) は[、Microsoft Teams](/microsoftteams/platform/overview)開発者向けドキュメントや[Microsoft](/graph/permissions-reference)Graph のアクセス許可のどこにも表示されません。 これは、この記事の目的に関する簡単な説明です。


| タイトル   | 説明    |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>調査中のアプリが要求しているアクセス許可を理解するには、次の表をガイドとして使用します。</li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>アプリまたはサービス自体を調査して、組織内でアクセスを許可するかどうかを決定します。 たとえば、ボットはユーザーからのメッセージを送受信します。エンタープライズ カスタム ボットを除き、ボットはコンプライアンスの境界の外に配置されます。 そのため、ボットを含むすべてのアプリでは、これらのアクセス許可が必要であり、少なくともそのリスク プロファイルを持っています。 </li></ul>|

「デバイスの[アクセス許可を要求する」タブもMicrosoft Teamsしてください](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。

## <a name="global-app-permissions-and-considerations"></a>グローバル アプリのアクセス許可と考慮事項

### <a name="required-permissions"></a>必要なアクセス許可

なし

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

- アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクでデータが使用されるデータを開示する必要があります。

- [リソース固有の同意は](resource-specific-consent.md) 、アプリが要求できる一連のアクセス許可を提供します。このアクセス許可は、アプリのインストール画面に表示されます。 リソース固有の同意アクセス許可の詳細については、「アクセス許可の参照Graph[参照してください](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

- アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合があります。 アプリがインストールされた後、アプリは同意プロンプトをGraphアクセス許可を要求できます。 詳細については、「アプリケーションの同意エクスペリエンス [について」AD参照してください](/azure/active-directory/develop/application-consent-experience)。 API のアクセス許可と同意は、Azure Portal で構成できます。 詳細については、「同意フレームワーク[のAzure Active Directory参照してください](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>ボットとメッセージング拡張機能

### <a name="required-permissions"></a>必要なアクセス許可

- RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ボットは、ユーザーからメッセージを受信して返信できます。<sup>1</sup>

- POST_MESSAGE_USER。 ユーザーがボットにメッセージを送信すると、ボットはユーザーダイレクト メッセージ (プロアクティブ メッセージとも呼ばれる) *をいつでも* 送信できます。

- GET_CHANNEL_LIST。 チームに追加されたボットは、チーム内のチャネルの名前と ID の一覧を取得できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

- IDENTITY。 チャネルで使用すると、アプリのボットは、チーム メンバーの基本的な ID 情報 (名、名、ユーザー プリンシパル名 [UPN]、電子メール アドレス) にアクセスできます。個人チャットまたはグループ チャットで使用されている場合、ボットはそれらのユーザーに対して同じ情報にアクセスできます。

- POST_MESSAGE_TEAM。 ユーザーがボットと話したことがない場合でも、アプリのボットがいつでも任意のチーム メンバーに直接 (プロアクティブ) メッセージを送信できます。

- 明示的なアクセス許可は次のとおりですが、RECEIVE_MESSAGE と REPLYTO_MESSAGE とボットを使用できるスコープ (マニフェストで宣言) によって暗黙的に示されます。
 
    - RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

- SEND_FILES、RECEIVE_FILES。<sup>2</sup> ボットが個人チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。

### <a name="considerations"></a>考慮事項

- ボットは、追加されたチーム、またはボットをインストールしたユーザーにのみアクセスできます。

- ボットは、ユーザーによって明示的に言及されたメッセージのみを受信します。 このデータは、企業ネットワークから出て行く。

- ボットは、自分が言及されている会話にのみ返信できます。

- ユーザーがボットと会話した後、ボットがユーザーの ID を格納している場合は、いつでもそのユーザーのダイレクト メッセージを送信できます。

- ボット メッセージにフィッシング詐欺サイトまたはマルウェア サイトへのリンクを含め、理論上は可能ですが、ボットはユーザー、テナント管理者、または Microsoft によってグローバルにブロックできます。

- ボットは、アプリが追加されたチーム メンバー、または個人チャットまたはグループ チャットの個々のユーザーの非常に基本的な ID 情報を取得 (および保存する可能性があります) できます。 これらのユーザーに関する詳細な情報を取得するには、ボットがユーザーにサインインを要求する必要があります (AD Azure Azure Active Directory)。

- ボットは、チーム内のチャネルの一覧を取得 (および格納できる場合があります) できます。このデータは企業ネットワークから出て行く。

- ファイルがボットに送信された場合、ファイルは企業ネットワークから出て行く。 ファイルの送受信には、ファイルごとにユーザーの承認が必要です。 

- 既定では、ボットはユーザーに代わって行動する機能を持つ必要がありますが、ボットはユーザーにサインインを要求できます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を実行できます。 これらの追加の内容は、ボットとユーザーのサインイン場所によって正確に異なります。ボットはに登録されている Azure AD アプリであり、独自のアクセス許可セットを持つ可能性 https://apps.dev.microsoft.com/ があります。

- ボットは、ユーザーがチームに追加またはチームから削除されるたびに通知されます。

- ボットは、ユーザーの IP アドレスや他の参照元情報を表示しません。 すべての情報は Microsoft から提供されます。 (1 つの例外があります。ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照元情報が表示されます)。

- 一方、メッセージング拡張機能には、ユーザーの IP アドレスと参照元情報が表示されます。

- アプリ のガイドライン (および AppSource レビュー プロセス) では、有効な目的のために(POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャット メッセージをユーザーに投稿する際に判断する必要があります。 不正使用が発生した場合、ユーザーはボットをブロックし、テナント管理者はアプリをブロックできます。また、必要に応じて Microsoft がボットを一中心にブロックできます。

<sup>1 一</sup> 部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。 これらは "通知のみ" ボットと呼ばれるが、この用語はボットが許可または許可されていない操作を参照しているのではなく、ボットが会話エクスペリエンスを公開したくないことを意味します。 Teamsこのフィールドを使用して、通常は有効になる UI の機能を無効にします。会話エクスペリエンスを公開するボットに比べて、ボットの実行が許可される操作は制限されません。

<sup>2</sup> アプリのファイルに基manifest.jsボット オブジェクトの supportsFiles ブールプロパティによって管理されます。

> [!NOTE]
> ボットに独自のサインインがある場合、ユーザーが初めてサインインする場合は、2 つ目の異なる同意エクスペリエンスがあります。
>
>現時点では、Teams アプリ (ボット、タブ、コネクタ、またはメッセージング拡張機能) 内の機能に関連付けられている Azure AD のアクセス許可は、ここに示されている Teams アクセス許可とは完全に分離されています。

## <a name="tabs"></a>タブ

タブは、Web サイト内で実行Teams。

### <a name="required-permissions"></a>必要なアクセス許可

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>オプションのアクセス許可

なし (現在)

### <a name="considerations"></a>考慮事項

- タブのリスク プロファイルは、ブラウザー タブで実行されている同じ Web サイトとほぼ同じです。 

- タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、それが存在する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、実行されているコンテキストも取得されます。 ただし、これらの ID をユーザーの情報にマップするには、タブでユーザーが Azure アカウントにサインインAD。

## <a name="connectors"></a>コネクタ

外部システムのイベントが発生すると、コネクタはチャネルにメッセージを投稿します。

### <a name="required-permissions"></a>必要なアクセス許可

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>オプションのアクセス許可

REPLYTO_CONNECTOR_MESSAGE。 特定のコネクタでは、アクション可能なメッセージがサポートされています。このメッセージを使用すると、GitHub の問題に応答を追加したり、Trello カードに日付を追加したりして、ユーザーはコネクタ メッセージに対して対象指定の応答を投稿できます。

### <a name="considerations"></a>考慮事項

- コネクタ メッセージを投稿するシステムは、メッセージを投稿しているユーザーまたはメッセージを受信したユーザーを知りません。受信者に関する情報は開示されません。 (Microsoft はテナントではなく、実際の受信者です。Microsoft は、チャネルへの実際の投稿を行います)。

- コネクタ メッセージがチャネルに投稿された場合、企業ネットワークからデータが送信されません。

- アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGE) をサポートするコネクタには、IP アドレスと参照元情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録された HTTP エンドポイントにルーティングされます。

- チャネルに対してコネクタが構成されるたび、そのコネクタ インスタンスの一意の URL が作成されます。 そのコネクタ インスタンスが削除された場合、URL は使用できなくなりました。

- コネクタ メッセージには添付ファイルを含めできません。

- コネクタ インスタンスの URL はシークレット/機密として扱う必要があります。その URL を持つすべてのユーザーは、電子メール アドレスのようにその URL に投稿できます。 そのため、スパムやフィッシングサイトやマルウェア サイトへのリンクが発生するリスクがあります。 その場合、チーム所有者はコネクタ インスタンスを削除できます。

- コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング/マルウェア リンクの送信が開始された場合、テナント管理者は新しいコネクタ インスタンスの作成を妨げる可能性があります。また、Microsoft はそれらを一本的にブロックできます。

> [!NOTE]
> 現在、アクション可能なメッセージをサポートしているコネクタを確認することはできません (REPLYTO_CONNECTOR_MESSAGEアクセス許可)。

## <a name="outgoing-webhooks"></a>送信 webhook

*送信 webhook は* 、チーム所有者またはチーム メンバーによって、その他の方法で作成されます。 これらは、アプリのTeams機能ではない。この情報は完全に含まれています。

### <a name="required-permissions"></a>必要なアクセス許可

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ユーザーからメッセージを受信して返信できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

- 送信 webhook はボットに似ていますが、権限は少なめです。 ボットと同様に、明示的に言及する必要があります。

- 送信 Webhook が登録されると、シークレットが生成されます。これにより、送信 webhook は、悪意のある攻撃者ではなく、送信者がMicrosoft Teamsを確認できます。 このシークレットはシークレットのままである必要があります。アクセス権を持つユーザーは、ユーザーを偽装Microsoft Teams。 シークレットが侵害された場合、送信 webhook を削除して再作成し、新しいシークレットが生成されます。

- シークレットを検証しない送信 webhook を作成することができますが、その場合は、その Webhook に対して実行することをお勧めします。

- メッセージの送受信以外に、送信 Webhook は多くのことを行えません。メッセージを事前に送信できない、ファイルを送受信できない、ボットが実行できる他の操作は、メッセージの受信と返信を除いて実行できます。