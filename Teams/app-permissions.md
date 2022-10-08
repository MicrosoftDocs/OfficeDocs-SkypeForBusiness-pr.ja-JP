---
title: Microsoft Teams アプリのアクセス許可と考慮事項
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理者は、Microsoft Teams アプリが組織から要求するデータとアクセス許可を確認できます。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64e63b4df818d792f722aed5b61315828a79bf76
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377135"
---
# <a name="information-accessed-and-actions-performed-by-teams-apps-and-admin-considerations"></a>Teams アプリと管理者の考慮事項によってアクセスされる情報とアクション

Microsoft Teams アプリは、1 つ以上の機能を、インストール、アップグレード、アンインストールできるアプリに集約します。 アプリの機能は次のとおりです。

* ボット
* メッセージングの拡張機能
* タブ
* コネクタ

管理者は、アプリのみを管理します。 ただし、アプリの機能がアプリの必要なアクセス許可とリスク プロファイルに影響を与えるため、この記事では機能レベルでのアクセス許可と考慮事項に焦点を当てています。 使用する場合、アプリはユーザーが同意し、ポリシーの観点から IT 担当者が管理します。

たとえば、`RECEIVE_MESSAGE` と `REPLYTO_MESSAGE` では、以下のアクセス許可は大文字で一覧表示され、図解と説明のみを目的としています。 これらの文字列またはアクセス許可は、[Microsoft Teams 開発者向けドキュメント](/microsoftteams/platform/overview)や [Microsoft Graph のアクセス許可](/graph/permissions-reference)のどこにも表示されません。

## <a name="global-app-permissions-and-considerations"></a>グローバル アプリのアクセス許可と考慮事項

### <a name="required-permissions"></a>必要なアクセス許可

なし

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

* アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクで使用されるデータを開示する必要があります。

* [リソース固有の同意](resource-specific-consent.md)は、アプリが要求でき、アプリのインストール画面に表示される一連のアクセス許可を提供します。 リソース固有の同意アクセス許可の詳細については、「[Graph のアクセス許可リファレンス](/graph/permissions-reference#teams-resource-specific-consent-permissions)」を参照してください。

* アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合もあります。 アプリのインストール後、アプリは同意プロンプトを通して Graph のアクセス許可を要求できます。 詳細については、「[Azure AD アプリケーションの同意エクスペリエンスを理解する](/azure/active-directory/develop/application-consent-experience)」を参照してください。 API のアクセス許可と同意は、Azure portal で構成できます。 詳細については、「[Azure Active Directory の同意フレームワーク](/azure/active-directory/develop/consent-framework)」を参照してください。

## <a name="bots-and-messaging-extensions"></a>ボットおよびメッセージングの拡張機能

### <a name="required-permissions"></a>必要なアクセス許可

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: ボットは、ユーザーからメッセージを受信し、それらに返信できます。<sup>1</sup>

* POST_MESSAGE_USER: ユーザーがボットにメッセージを送信した後、ボットはユーザー ダイレクト メッセージ (*プロアクティブ メッセージ* とも呼ばれます) をいつでも送信できます。

* GET_CHANNEL_LIST: Teams に追加されたボットは、チーム内のチャネルの名前と ID の一覧を取得できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

* IDENTITY: チャネルで使用されている場合、アプリのボットはチーム メンバーの基本的な ID 情報 (名、姓、ユーザー プリンシパル名 [UPN]、メール アドレス) にアクセスできます。 個人チャットまたはグループ チャットで使用すると、ボットはそれらのユーザーと同じ情報にアクセスできます。

* POST_MESSAGE_TEAM: アプリのボットは、ユーザーがボットと対話したことがない場合でも、いつでもチーム メンバーに直接 (プロアクティブ) メッセージを送信できます。

* 以下に示す内容は、明示的なアクセス許可ではありませんが、RECEIVE_MESSAGE と REPLYTO_MESSAGE、およびボットを使用できる範囲 (マニフェストで宣言) によって暗黙的に示されます。

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* 以下に示す内容は、明示的なアクセス許可ではありませんが、RECEIVE_MESSAGE と REPLYTO_MESSAGE、およびボットを使用できる範囲 (マニフェストで宣言) によって暗黙的に示されます。

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* SEND_FILES、RECEIVE_FILES:<sup>2</sup> ボットが個人用チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。

### <a name="considerations"></a>考慮事項

* ボットは、追加されたチームまたはそれらをインストールしたユーザーにのみアクセスできます。

* ボットは、ユーザーが明示的にメンションしたメッセージのみを受信します。 このデータは、企業ネットワークを離れます。

* ボットは、メンションされている会話にのみ返信できます。

* ユーザーがボットと会話するとき、ボットがユーザーの ID を格納している場合、ユーザーのダイレクト メッセージはいつでも送信できます。

* 理論的には、ボット メッセージにフィッシング サイトやマルウェア サイトへのリンクを含めることができます。 ただし、ボットは、ユーザー、テナント管理者、または Microsoft からグローバルにブロックできます。 [アプリの検証と検証のチェック](overview-of-app-validation.md) により、不正なアプリが Teams ストアで使用できないことが確認されます。

* ボットは、アプリが追加されたチーム メンバー、または個人チャットまたはグループ チャットの個々のユーザーの基本的な ID 情報を取得 (および格納する場合があります) できます。 これらのユーザーの詳細を取得するには、ボットが Azure Active Directory (Azure AD) にサインインする必要があります。

* ボットは、チーム内のチャネルの一覧を取得 (および格納する場合もあります) できます。このデータは企業ネットワークを離れます。

* 既定では、ボットがユーザーに代わって行動する機能はありませんが、ボットはユーザーにサインインを依頼できます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を行うことができます。 その他の内容は、ボットとユーザーがサインインする場所によって正確に異なります。ボットは https://apps.dev.microsoft.com/ で登録された Azure AD アプリであり、独自のアクセス許可のセットを持つことができます。

* ファイルがボットに送信されると、ファイルは企業ネットワークを離れます。 ファイルの送受信には、ファイルごとにユーザーの承認が必要です。

* ボットは、ユーザーがチームに追加または削除されるたびに通知されます。

* ボットには、ユーザーの IP アドレスやその他の参照元情報は表示されません。 すべての情報は Microsoft から提供されています。 (1 つの例外: ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照元の情報が表示されます)。

* 一方、メッセージング拡張機能には、ユーザーの IP アドレスと参照元の情報が表示されます。

* アプリ ガイドライン (および AppSource レビュー プロセス) では、有効な目的のために (POST_MESSAGE_TEAM アクセス許可を介して) ユーザーに個人用チャット メッセージを投稿する裁量が必要です。 不正使用が発生した場合、ユーザーはボットをブロックでき、テナント管理者はアプリをブロックでき、Microsoft は必要に応じてボットを一元的にブロックできます。

<sup>1</sup> 一部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。 "通知専用" ボットと呼ばれますが、この用語はボットが許可されているかどうかを指すのではなく、ボットが会話エクスペリエンスを公開する必要がないことを意味します。 Teams は、このフィールドを使用して、通常は有効になる UI の機能を無効にします。ボットは、会話エクスペリエンスを公開するボットと比較して、許可される操作に制限されません。

<sup>2</sup> アプリの `manifest.json` ファイル内のボット オブジェクトの supportsFiles ブール値プロパティで管理されます。

> [!NOTE]
> ボットに独自のサインインがある場合は、ユーザーの初回サインイン時の同意エクスペリエンスとは異なる 2 つ目のエクスペリエンスがあります。
>
>現時点では、Teams アプリ内の機能 (ボット、タブ、コネクタ、またはメッセージング拡張機能) に関連付けられている Azure AD のアクセス許可は、こちらに一覧表示されている Teams のアクセス許可とは完全に分離されています。

## <a name="tabs"></a>タブ

タブは、Teams 内で実行中の Web サイトです。

### <a name="required-permissions"></a>必要なアクセス許可

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>オプションのアクセス許可

なし (現在)

### <a name="considerations"></a>考慮事項

* タブのリスク プロファイルは、ブラウザー タブで実行中のものと同じ Web サイトとほぼ同じです。

* タブは、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、それが存在する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、タブを実行中のコンテキストも取得します。 ただし、これらの ID をユーザーの情報にマッピングするには、タブでユーザーを Azure AD にサインインさせる必要があります。

## <a name="connectors"></a>コネクタ

コネクタは、外部システムでイベントが発生したときにチャネルにメッセージを投稿します。

### <a name="required-permissions"></a>必要なアクセス許可

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>オプションのアクセス許可

REPLYTO_CONNECTOR_MESSAGE。 特定のコネクタでは、アクション可能なメッセージがサポートされています。たとえば、GitHub の問題に対する応答を追加したり、Trello カードに日付を追加したりすることで、ユーザーはコネクタ メッセージにターゲットを設定した返信を投稿できます。

### <a name="considerations"></a>考慮事項

* コネクタ メッセージを投稿するシステムには、受信者に関する情報が開示されず、誰に投稿しているか、誰がメッセージを受け取るかを知りません。 (Microsoft は実際の受信者であり、テナントではありません。Microsoft は、チャネルへの実際の投稿を行います。)

* コネクタ メッセージがチャネルに投稿される際に、データが企業ネットワークを離れることはありません。

* アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートするコネクタには、IP アドレスと参照元の情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録されていた HTTP エンドポイントにルーティングされます。

* コネクタがチャネル用に構成されるたびに、そのコネクタ インスタンスの一意の URL が作成されます。 そのコネクタ インスタンスが削除された場合、URL は使用できなくなります。

* コネクタ メッセージに添付ファイルを含めることはできません。

* コネクタ インスタンス URL は、シークレット/機密として扱う必要があります。その URL を持つすべてのユーザーは、電子メール アドレスなど、その URL に投稿できます。 そのため、スパムやフィッシング サイトやマルウェア サイトにリンクされるリスクがあります。 そのような問題が発生した場合、チームの所有者はコネクタ インスタンスを削除できます。

* コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング/マルウェアのリンクの送信を開始した場合、テナント管理者は新しいコネクタ インスタンスを作成できないようにし、Microsoft はそれらを一元的にブロックできます。

> [!NOTE]
> 現時点では、実行可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートしているコネクタを把握することはできません。

## <a name="outgoing-webhooks"></a>送信 Webhook

_送信 Webhook_ は、チームの所有者またはチーム メンバーによって作成されます。 この機能は、Teams アプリの機能ではありません。この情報は完全に含まれています。

### <a name="required-permissions"></a>必要なアクセス許可

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 ユーザーからメッセージを受信し、それらに返信できます。

### <a name="optional-permissions"></a>オプションのアクセス許可

なし

### <a name="considerations"></a>考慮事項

* 送信 Webhook はボットに似ていますが、特権はボットより少なくなります。 ボットと同様に、明示的にメンションする必要があります。

* 送信 Webhook が登録されると、シークレットが生成されます。これにより、送信 Webhook は、送信者が悪意のある攻撃者ではなく、Microsoft Teams であることを確認できます。 このシークレットはシークレットのまま維持する必要があります。アクセス権を持つすべてのユーザーは、Microsoft Teams になりすますことができます。 シークレットが侵害された場合は、送信 Webhook を削除して再作成し、新しいシークレットを生成してください。

* シークレットを検証しない送信 Webhook を作成することはできますが、そうしないことをお勧めします。

* メッセージの受信と返信以外に、送信 Webhook は多くのことを行うことはできません。たとえば、メッセージをプロアクティブに送信できず、ファイルを送受信できず、メッセージの受信と返信以外にボットが行うことができる操作を実行することはできません。
