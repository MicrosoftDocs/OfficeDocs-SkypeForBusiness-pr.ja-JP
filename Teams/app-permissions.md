---
title: Microsoft Teams アプリのアクセス許可と考慮事項
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理アプリが組織に要求Microsoft Teamsデータとアクセス許可を確認できます。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9ce3fccd8974bd7f8cba04d01bf16738772ea11
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124182"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams アプリのアクセス許可と考慮事項

Microsoft Teams アプリは、1 つ以上の機能を、インストール、アップグレード、アンインストールできるアプリに集約する方法です。 アプリの機能は次のとおりです。

* ボット
* メッセージング拡張機能
* タブ
* コネクタ

管理者は、アプリのみを管理します。 ただし、この記事では、アプリの機能がアプリの必要なアクセス許可とリスク プロファイルに影響を与えるので、機能レベルでのアクセス許可と考慮事項に焦点を当てています。 使用のために、アプリはユーザーによって同意され、ポリシーの観点から IT 担当者によって管理されます。

たとえば `RECEIVE_MESSAGE` 、以下に示すアクセス許可は大文字で示されており `REPLYTO_MESSAGE` 、説明と説明のみを目的としています。 これらの文字列またはアクセス許可は、[Microsoft Teams開発者向けドキュメント](/microsoftteams/platform/overview)や [Microsoft Graphのアクセス許可](/graph/permissions-reference)のどこにも表示されません。

## <a name="global-app-permissions-and-considerations"></a>グローバル アプリのアクセス許可と考慮事項

### <a name="required-permissions"></a>必要なアクセス許可

なし

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

* アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクで使用されるデータを開示する必要があります。

* [リソース固有の同意](resource-specific-consent.md) は、アプリが要求できる一連のアクセス許可を提供します。アプリのインストール画面に表示されます。 リソース固有の同意アクセス許可の詳細については、「[Graphアクセス許可のリファレンス」を参照](/graph/permissions-reference#teams-resource-specific-consent-permissions)してください。

* アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合もあります。 アプリをインストールした後、アプリは同意プロンプトを使用してGraphアクセス許可を要求できます。 詳細については、「 [Azure AD アプリケーションの同意エクスペリエンスについて](/azure/active-directory/develop/application-consent-experience)」を参照してください。 API のアクセス許可と同意は、Azure portalで構成できます。 詳細については、[同意フレームワークAzure Active Directory](/azure/active-directory/develop/consent-framework)参照してください。

## <a name="bots-and-messaging-extensions"></a>ボットとメッセージング拡張機能

### <a name="required-permissions"></a>必要なアクセス許可

* RECEIVE_MESSAGE、REPLYTO_MESSAGE: ボットは、ユーザーからメッセージを受信し、それらに返信できます。<sup>1</sup>

* POST_MESSAGE_USER: ユーザーがボットにメッセージを送信した後、ボットはユーザーダイレクト メッセージ ( *プロアクティブ メッセージ* とも呼ばれます) をいつでも送信できます。

* GET_CHANNEL_LIST: チームに追加されたボットは、チーム内のチャネルの名前と ID の一覧を取得できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

* IDENTITY: チャネルで使用されている場合、アプリのボットはチーム メンバーの基本的な ID 情報 (名、姓、ユーザー プリンシパル名 [UPN]、電子メール アドレス) にアクセスできます。 個人チャットまたはグループ チャットで使用すると、ボットはそれらのユーザーと同じ情報にアクセスできます。

* POST_MESSAGE_TEAM: アプリのボットは、ユーザーがボットと対話したことがない場合でも、いつでもチーム メンバーに直接 (プロアクティブ) メッセージを送信できます。

* 次は明示的なアクセス許可ではありませんが、RECEIVE_MESSAGEとREPLYTO_MESSAGE、およびボットを使用できるスコープ (マニフェストで宣言) によって暗黙的に示されています。

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* 次は明示的なアクセス許可ではありませんが、RECEIVE_MESSAGEとREPLYTO_MESSAGE、およびボットを使用できるスコープ (マニフェストで宣言) によって暗黙的に示されています。

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* SEND_FILES、RECEIVE_FILES:<sup>2</sup> ボットが個人用チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。

### <a name="considerations"></a>考慮事項

* ボットは、追加されたチームまたはそれらをインストールしたユーザーにのみアクセスできます。

* ボットは、ユーザーが明示的に言及したメッセージのみを受信します。 このデータは、企業ネットワークから離れる。

* ボットは、自分が言及されている会話にのみ返信できます。

* ユーザーがボットと会話するとき、ボットがユーザーの ID を格納している場合、ユーザーのダイレクト メッセージはいつでも送信できます。

* 理論的には、ボット メッセージにフィッシングサイトやマルウェア サイトへのリンクを含めることができる。 ただし、ボットは、ユーザー、テナント管理者、または Microsoft によってグローバルにブロックできます。 [アプリの検証と検証のチェック](overview-of-app-validation.md)により、偽のアプリがTeams ストアで使用できないことが保証されます。

* ボットは、アプリが追加されたチーム メンバー、または個人チャットまたはグループ チャットの個々のユーザーの基本的な ID 情報を取得 (および格納する場合があります) できます。 これらのユーザーに関する詳細情報を取得するには、ボットがAzure Active Directory (Azure AD) にサインインする必要があります。

* ボットは、チーム内のチャネルの一覧を取得 (および格納) できます。このデータは企業ネットワークから離れる。

* 既定では、ボットにはユーザーに代わって行動する機能はありませんが、ボットはユーザーにサインインを求めることができます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を行うことができます。 その他の内容は、ボットとユーザーがサインインする場所によって正確に異なります。ボットは Azure AD アプリに https://apps.dev.microsoft.com/ 登録されており、独自のアクセス許可のセットを持つことができます。

* ファイルがボットに送信されると、ファイルは企業ネットワークから離れる。 ファイルの送受信には、ファイルごとにユーザーの承認が必要です。

* 既定では、ボットにはユーザーに代わって行動する機能はありませんが、ボットはユーザーにサインインを求めることができます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を行うことができます。 これらの追加機能は、ボットとユーザーがサインインする場所によって正確に異なります。ボットは [、アプリケーション登録ポータル](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) に登録された Azure AD アプリであり、独自のアクセス許可のセットを持つことができます。

* ボットは、ユーザーがチームに追加または削除されるたびに通知されます。

* ボットには、ユーザーの IP アドレスやその他の参照元情報は表示されません。 すべての情報は Microsoft から提供されています。 (1 つの例外があります。ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照元の情報が表示されます)。

* 一方、メッセージング拡張機能には、ユーザーの IP アドレスと参照元の情報が表示されます。

* アプリガイドライン (および AppSource レビュー プロセス) では、有効な目的のために (POST_MESSAGE_TEAM アクセス許可を使用して) ユーザーに個人用チャット メッセージを投稿する裁量が必要です。 不正使用が発生した場合、ユーザーはボットをブロックでき、テナント管理者はアプリをブロックでき、Microsoft は必要に応じてボットを一元的にブロックできます。

<sup>1</sup> 一部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。 "通知専用" ボットと呼ばれますが、この用語はボットが許可されているか許可されていないかを指すのではなく、ボットが会話エクスペリエンスを公開したくないことを意味します。 Teamsこのフィールドを使用して、通常は有効になる UI の機能を無効にします。ボットは、会話エクスペリエンスを公開するボットと比較して許可される操作に制限されません。

<sup>2</sup> アプリのファイル内 `manifest.json` のボット オブジェクトの supportsFiles Boolean プロパティによって管理されます。

> [!NOTE]
> ボットに独自のサインインがある場合は、ユーザーが初めてサインインする際の同意エクスペリエンスとは異なる 2 つ目があります。
>
>現時点では、Teams アプリ内の機能 (ボット、タブ、コネクタ、またはメッセージング拡張機能) に関連付けられている Azure AD アクセス許可は、ここに示すTeamsアクセス許可とは完全に分離されています。

## <a name="tabs"></a>タブ

タブは、Teams内で実行されている Web サイトです。

### <a name="required-permissions"></a>必要なアクセス許可

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>オプションのアクセス許可

None (現在)

### <a name="considerations"></a>考慮事項

* タブのリスク プロファイルは、ブラウザー タブで実行されているのと同じ Web サイトとほぼ同じです。

* タブは、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、それが存在するMicrosoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、実行されているコンテキストも取得します。 ただし、これらの ID をユーザーの情報にマップするには、タブでユーザーを Azure AD にサインインさせる必要があります。

## <a name="connectors"></a>コネクタ

コネクタは、外部システムのイベントが発生したときにチャネルにメッセージを投稿します。

### <a name="required-permissions"></a>必要なアクセス許可

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>オプションのアクセス許可

REPLYTO_CONNECTOR_MESSAGE。 特定のコネクタでは、アクション可能なメッセージがサポートされています。たとえば、GitHubの問題に対する応答を追加したり、Trello カードに日付を追加したりすることで、ユーザーはコネクタ メッセージにターゲットを絞った返信を投稿できます。

### <a name="considerations"></a>考慮事項

* コネクタ メッセージを投稿するシステムは、受信者に関する情報が開示されないという、誰に投稿しているか、誰がメッセージを受け取るかを知りません。 (Microsoft は実際の受信者であり、テナントではありません。Microsoft は、チャネルへの実際の投稿を行います。)

* コネクタ メッセージがチャネルにポストされるときに、企業ネットワークからデータが残されることはありません。

* アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートするコネクタには、IP アドレスと参照元の情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録されていた HTTP エンドポイントにルーティングされます。

* コネクタがチャネル用に構成されるたびに、そのコネクタ インスタンスの一意の URL が作成されます。 そのコネクタ インスタンスが削除された場合、URL は使用できなくなります。

* コネクタ メッセージに添付ファイルを含めることはできません。

* コネクタ インスタンスの URL はシークレット/機密として扱う必要があります。その URL を持つすべてのユーザーは、電子メール アドレスなど、その URL に投稿できます。 そのため、スパムやフィッシングサイトやマルウェア サイトへのリンクのリスクがあります。 その場合、チーム所有者はコネクタ インスタンスを削除できます。

* コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング/マルウェア のリンクの送信を開始した場合、テナント管理者は新しいコネクタ インスタンスの作成を禁止し、Microsoft がそれらを一元的にブロックできます。

> [!NOTE]
> 現時点では、実行可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートしているコネクタを把握することはできません。

## <a name="outgoing-webhooks"></a>送信 Webhook

_送信 Webhook_ は、チームの所有者またはチーム メンバーによって作成されます。 これらは、Teams アプリの機能ではありません。この情報は完全に含まれています。

### <a name="required-permissions"></a>必要なアクセス許可

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ユーザーからメッセージを受信し、それらに返信できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

* 送信 Webhook はボットに似ていますが、特権が少なくなります。 ボットと同様に、明示的に言及する必要があります。

* 送信 Webhook が登録されると、シークレットが生成されます。これにより、送信 Webhook は、悪意のある攻撃者ではなく、送信者がMicrosoft Teamsされていることを確認できます。 このシークレットはシークレットのままである必要があります。アクセス権を持つすべてのユーザーは、Microsoft Teamsを偽装できます。 シークレットが侵害された場合は、送信 Webhook を削除して再作成でき、新しいシークレットが生成されます。

* シークレットを検証しない送信 Webhook を作成することは可能ですが、それに対して推奨されます。

* メッセージの受信と返信以外に、送信 Webhook は多くのことを行うことはできません。メッセージをプロアクティブに送信できない、ファイルを送受信できない、メッセージの受信と返信以外にボットが行うことができる他の操作は実行できません。
