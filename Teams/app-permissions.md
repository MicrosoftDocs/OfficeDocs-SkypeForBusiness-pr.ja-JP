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
description: 管理者は、Microsoft Teams アプリが組織に要求しているデータとアクセス許可について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e6628467d4300130c39a3bade87919fb064a14f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874707"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams アプリのアクセス許可と考慮事項

Microsoft Teams アプリは、インストール、アップグレード、アンインストールできる 1 つ以上の機能をアプリ パッケージに集約する方法です。  次のような機能があります。

- ボット
- メッセージング拡張機能
- タブ
- コネクタ

アプリはユーザーによって同意され、ポリシーの観点から IT によって管理されます。 ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルは、アプリに含まれる機能の権限とリスク プロファイルによって定義されます。 そのため、この記事では、機能レベルでのアクセス許可と考慮事項について説明します。

RECEIVE_MESSAGE や REPLYTO_MESSAGE など、大文字で次に示すアクセス許可は [、Microsoft Teams](https://aka.ms/teamsdevdocs) の開発者ドキュメントや [Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)のアクセス許可のどこにも表示されません。 これらは、この記事の目的に関する簡単な説明です。


| タイトル   | 説明    |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>調査中のアプリが要求しているアクセス許可を理解するには、次の表をガイドとして使用します。</li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>アプリまたはサービス自体を調査して、組織内でアクセスを許可するかどうかを決定します。 たとえば、ボットはユーザーからのメッセージを送受信し、エンタープライズ カスタム ボットを除き、コンプライアンスの境界の外に配置されます。 そのため、ボットを含むアプリには、これらのアクセス許可が必要であり、少なくともそのリスク プロファイルが含まれています。 </li></ul>|

「Microsoft [Teams タブのデバイスアクセス許可を要求する」も参照してください](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。

## <a name="global-app-permissions-and-considerations"></a>グローバル アプリのアクセス許可と考慮事項

### <a name="required-permissions"></a>必要なアクセス許可

なし

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

- アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクでデータが使用される内容を公開する必要があります。

- [リソース固有の同意は](resource-specific-consent.md) 、アプリが要求できる一連のアクセス許可を提供し、アプリのインストール画面に表示されます。 リソース固有の同意アクセス許可の詳細については、Graph のアクセス許可 [のリファレンスを参照してください](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)。

- また、アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合があります。 アプリがインストールされた後、アプリは同意のプロンプトで Graph のアクセス許可を要求する場合があります。 詳細については、「Azure とアプリケーションの同意 [のADを参照してください](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)。 Azure Portal で API のアクセス許可と同意を構成できます。 詳細については [、Azure Active Directory 同意フレームワークを参照してください](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>ボットとメッセージング拡張機能

### <a name="required-permissions"></a>必要なアクセス許可

- RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ボットはユーザーからのメッセージを受信して、返信することができます。<sup>1</sup>

- POST_MESSAGE_USER。 ユーザーがボットにメッセージを送信すると、ボットはユーザーのダイレクト メッセージ (いつでもプロアクティブ メッセージとも呼 *ばれる)* を送信できます。

- GET_CHANNEL_LIST。 チームに追加されたボットは、チーム内のチャネルの名前と ID のリストを取得できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

- IDENTITY。 チャネルで使用される場合、アプリのボットは、チーム メンバーの基本的な ID 情報 (名、名、ユーザー プリンシパル名 [UPN]、メール アドレス) にアクセスできます。ボットは、個人チャットまたはグループ チャットで使用される場合、それらのユーザーの同じ情報にアクセスできます。

- POST_MESSAGE_TEAM。 ユーザーが以前にボットと話したことがない場合でも、アプリのボットがチーム メンバーに直接 (積極的に) メッセージを送信できます。

- 次に示すのは明示的なアクセス許可ではなく、RECEIVE_MESSAGE と REPLYTO_MESSAGE、およびボットを使用できる範囲 (マニフェストで宣言) によって示されています。
 
    - RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

- SEND_FILES、RECEIVE_FILES。<sup>2</sup> ボットが個人チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。

### <a name="considerations"></a>考慮事項

- ボットは、追加されたチーム、またはボットをインストールしたユーザーにのみアクセスできます。

- ボットは、ユーザーが明示的に言及したメッセージのみを受信します。 このデータは企業ネットワークから離れ、

- ボットは、自分が言及されている会話にのみ返信できます。

- ユーザーがボットと会話した後、ボットがユーザーの ID を保存している場合、いつでもそのユーザーのダイレクト メッセージを送信できます。

- 理論上は、ボット メッセージにフィッシング詐欺サイトやマルウェア サイトへのリンクを含め込む可能性がありますが、ボットはユーザー、テナント管理者、または Microsoft がグローバルにブロックすることができます。

- ボットは、アプリが追加されたチーム メンバー、または個人またはグループ チャットの個々のユーザーに対して、非常に基本的な ID 情報を取得 (および保存できる場合があります) できます。 これらのユーザーに関する詳細を取得するには、ボットが Azure Active Directory (Azure Active Directory) へのサインインを要求AD。

- ボットはチーム内のチャネルのリストを取得 (および保存) できます。このデータは企業ネットワークから離れ、

- ファイルがボットに送信された場合、ファイルは企業ネットワークから離れ、 ファイルの送受信には、ファイルごとにユーザーの承認が必要です。 

- 既定では、ボットにはユーザーの代わりに行動する機能が与えらされませんが、ボットはユーザーにサインインを要求できます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を行います。 これらの追加の内容は、ボットとユーザーがサインインする場所によって正確に異なります。ボットは Azure AD アプリで登録され、独自のアクセス許可セットを持つ可能性があります https://apps.dev.microsoft.com/ 。

- ボットは、ユーザーがチームに追加またはチームから削除されるたびに通知されます。

- ボットには、ユーザーの IP アドレスや他の参照先情報は表示できません。 すべての情報は Microsoft から取得されます。 (1 つの例外があります。ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照先情報が表示されます)。

- 一方、メッセージング拡張機能では、ユーザーの IP アドレスと参照元情報が表示されます。

- アプリのガイドライン (および AppSource のレビュー プロセス) では、有効な目的のために (POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャット メッセージをユーザーに投稿する際に、任意の裁量が必要です。 悪用が発生した場合、ユーザーはボットをブロックし、テナント管理者はアプリをブロックし、必要に応じて Microsoft がボットを一中心にブロックすることができます。

<sup>1 一</sup> 部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。 ボットは "通知専用" ボットと呼ばれるが、この用語はボットが許可または許可されていない操作を参照しているのではなく、ボットが会話エクスペリエンスを公開したくないことを意味します。 Teams では、通常は有効になる UI の機能を無効にするには、このフィールドを使用します。ボットは、会話エクスペリエンスを公開するボットと比べて、許可される操作に制限されません。

<sup>2</sup> アプリのファイル上のボット オブジェクトの supportsFiles Boolean manifest.jsによって制御されます。

> [!NOTE]
> ボットが独自のサインインを持っている場合は、ユーザーが初めてサインインする場合、別の同意エクスペリエンスがあります。
>
>現時点では、Teams アプリ (ボット、タブ、コネクタ、メッセージング拡張機能) 内の任意の機能に関連付けられている Azure AD のアクセス許可は、ここに記載されている Teams のアクセス許可とは完全に分離されています。

## <a name="tabs"></a>タブ

タブは、Teams 内で実行されている Web サイトです。

### <a name="required-permissions"></a>必要なアクセス許可

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>オプションのアクセス許可

なし (現在)

### <a name="considerations"></a>考慮事項

- タブのリスク プロファイルは、ブラウザー タブで実行されている同じ Web サイトとほぼ同じです。 

- タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、存在する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、実行されているコンテキストも取得されます。 ただし、これらの ID をユーザーの情報にマップするには、タブでユーザーが Azure AD にサインインする必要があります。

## <a name="connectors"></a>コネクタ

コネクタは、外部システムでイベントが発生した場合にメッセージをチャネルに投稿します。

### <a name="required-permissions"></a>必要なアクセス許可

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>オプションのアクセス許可

REPLYTO_CONNECTOR_MESSAGE。 特定のコネクタは、GitHub の問題への応答を追加したり、Trello カードに日付を追加したりして、ユーザーがコネクタ メッセージに対象指定の返信を投稿できる、アクション可能なメッセージをサポートしています。

### <a name="considerations"></a>考慮事項

- コネクタ メッセージを投稿するシステムは、メッセージの投稿先またはメッセージを受信したユーザーを知りません。受信者に関する情報は公開されません。 (Microsoft はテナントではなく、実際の受信者です。Microsoft は、チャネルへの実際の投稿を行います)。

- コネクタ メッセージがチャネルに投稿された場合、企業ネットワークからデータが削除されません。

- アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートするコネクタには、IP アドレスと参照元の情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録された HTTP エンドポイントにルーティングされます。

- チャネルに対してコネクタが構成されるたび、そのコネクタ インスタンスの一意の URL が作成されます。 そのコネクタ インスタンスが削除された場合、URL は使用できなくなりました。

- コネクタ メッセージに添付ファイルを含めできません。

- コネクタ インスタンスの URL は秘密/機密として扱う必要があります。その URL を持つすべてのユーザーは、メール アドレスのようにその URL に投稿できます。 そのため、スパムやフィッシングやマルウェア サイトへのリンクのリスクがあります。 その場合、チーム所有者はコネクタ インスタンスを削除できます。

- コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング詐欺/マルウェア リンクの送信を開始した場合、テナント管理者は新しいコネクタ インスタンスの作成を防止し、Microsoft がそれらを一本的にブロックできます。

> [!NOTE]
> 現在のところ、どのコネクタがアクション可能なメッセージ (アクセス許可を持つ) をサポートREPLYTO_CONNECTOR_MESSAGEできません。

## <a name="outgoing-webhooks"></a>送信 Webhooks

*送信 Webhook は* 、チームの所有者またはチーム メンバーがその他の方法で作成します。 Teams アプリの機能ではない。この情報は、完了のために含まれています。

### <a name="required-permissions"></a>必要なアクセス許可

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ユーザーからのメッセージを受信して返信できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

- 送信 Webhook はボットに似ていますが、権限は少なめです。 ボットと同様に、明示的に言及する必要があります。

- 送信 Webhook が登録されると、秘密情報が生成されます。これにより、送信 Webhook は、悪意のある攻撃者とは対照的に、送信者が Microsoft Teams である確認を行います。 この秘密は秘密のままです。アクセス権を持つユーザーは誰でも Microsoft Teams を偽装できます。 シークレットが侵害された場合、送信 Webhook を削除して再び作成すると、新しいシークレットが生成されます。

- 秘密を検証しない送信 Webhook を作成することができますが、その場合はお勧めします。

- 送信 Webhook は、メッセージの送受信以外に、メッセージを積極的に送信できない、ファイルを送受信できない、ボットが実行できるその他の操作 (メッセージの受信と返信を除く) など、多くのことを行えません。
