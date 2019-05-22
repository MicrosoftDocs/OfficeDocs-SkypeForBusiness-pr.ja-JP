---
title: Microsoft Teams アプリのアクセス許可と考慮事項
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 組織から要求されているデータおよびアクセス許可アプリについて説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: b99507dcb37d86879bd495655da3d6f88a06f64a
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344734"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams アプリのアクセス許可と考慮事項

Microsoft Teams アプリは、1つ以上の機能をインストール、アップグレード、アンインストールできる_アプリパッケージ_に集約するための手段です。 次のような機能があります。

-   ボット
-   メッセージングの拡張機能
-   タブ
-   コネクタ

アプリはユーザーによって各人され、ポリシーの観点から管理されます。 ただし、ほとんどの場合、アプリのアクセス許可とリスクプロファイルは、アプリに含まれる機能の権限とリスクのプロファイルによって定義されます。 したがって、この記事では、権限とその機能レベルに関する考慮事項について説明します。

RECEIVE_MESSAGE や REPLYTO_MESSAGE などの大文字で示されているアクセス許可は、 [Microsoft Teams の開発者向けドキュメント](https://aka.ms/teamsdevdocs)または[microsoft Graph のアクセス許可](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)のどこにも表示されません。 これらは、この記事の目的について簡単に説明しています。


|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>次の表を参考にして、調査しているアプリで要求されているアクセス許可について理解してください。</li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>アプリまたはサービス自体を調査して、組織内でのアクセスを許可するかどうかを決定します。 たとえば、ボットはユーザーからのメッセージを送受信します。また、エンタープライズ基幹業務用のボットを除いて、これらはコンプライアンスの境界外にあります。 そのため、bot を含むすべてのアプリには、これらのアクセス許可が必要であり、少なくともそのリスクのプロファイルが設定されています。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>グローバルアプリのアクセス許可と考慮事項

<table>
  <tr>
    <th width="25%">必要なアクセス許可</th>
    <th width="25%">オプションの権限</th>
    <th width="50%">考慮事項</th>
  </tr>
  <tr>
    <td valign="top">なし</td>
    <td valign="top">なし</td>
    <td valign="top">アプリは、使用するデータと、利用規約およびプライバシーポリシーへのリンクでデータがどのように使用されているかを公開する必要があります。</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>ボットとメッセージングの拡張機能

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">必要なアクセス許可</th>
    <th width="25%">オプションの権限</th>
    <th width="50%">考慮事項</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. ボットは、ユーザーからのメッセージを受信して返信することができます。<sup>1</sup></li><li>POST_MESSAGE_USER. ユーザーがボットにメッセージを送信した後、ボットはユーザーのダイレクトメッセージ (<em>予防的メッセージ</em>とも呼ばれます) をいつでも送信できます。</li><li>GET_CHANNEL_LIST. Teams に追加されたボットは、チーム内のチャネルの名前と Id の一覧を取得できます。</li></ul></td>
    <td valign="top"><ul><li>身分. チャネルで it& # 39; s を使用すると、app& # 39; の bot は、チームメンバーの基本的な id 情報 (名、姓、ユーザープリンシパル名 [UPN]、メールアドレス) にアクセスできます。個人またはグループチャットで it& # 39; s を使用している場合、bot はユーザーに対して同じ情報にアクセスできます。</li><li> POST_MESSAGE_TEAM. ユーザーが以前にボットに話したことがない場合でも、app& # 39; ボットが、任意のチームメンバーに対して直接 (予防的な) メッセージを送信することを許可します。</li><li>次に示すのは、明示的な権限ではなく、RECEIVE_MESSAGE と REPLYTO_MESSAGE によって暗黙的に指定されたものであり、マニフェストで宣言されているボットを使うことができるスコープです。 <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup>個人チャットでファイルを送受信できるかどうかを制御します (グループチャットまたはチャネルではまだサポートされていません)。</li></ul></td>
    <td valign="top"><ul><li>ボットは、they& # 39; ve が追加されたか、インストールされているユーザーにのみアクセスできます。</li><li>ボットは、they& # 39 で、ユーザーによって明示的にメンションされたメッセージのみを受け取ります。 このデータは企業ネットワークから離れています。</li><li>    ボットは、they& # 39; 再メンションされた会話にのみ返信できます。</li><li>ユーザーがボットを使用している場合、ボットが user& # 39; s ID を保存していれば、いつでもそのユーザーにダイレクトメッセージを送信できます。 </li><li>ボットメッセージには、フィッシングまたはマルウェアサイトへのリンクが含まれていても、ユーザー、テナント管理者、または Microsoft によってグローバルにブロックされている可能性があります。 </li><li>Bot は、アプリが追加されたチームメンバー、または個人またはグループチャットの個々のユーザーに対して、非常に基本的な id 情報を取得 (および保存する可能性があります) することができます。 これらのユーザーについての詳細情報を入手するには、ボットが Azure Active Directory (Azure AD) にサインインする必要があります。 </li><li>Bot は、チーム内のチャネルの一覧を取得 (および保存する可能性があります) することができます。このデータは企業ネットワークから離れています。 </li><li>ボットにファイルが送信されると、ファイルは企業ネットワークから脱退します。 ファイルを送受信するには、各ファイルに対してユーザーの承認が必要です。 </li><li>既定では、ボット don& # 39; t はユーザーの代理として動作する機能を備えていますが、ボットはユーザーにサインインを求めることができます。ユーザーがサインインするとすぐに、ボットには追加の項目を実行できるアクセストークンがあります。 このような追加事項は、ボットとユーザがサインインする場所によって異なります。ボットは、に<a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a>登録されている Azure AD アプリであり、独自の権限を設定できます。</li><li>ユーザーがチームに追加または削除されるたびに、ボットに通知されます。</li><li>ボット don& # 39; t 「users& # 39;」を参照してください。IP アドレスまたはその他の参照情報。 すべての情報は Microsoft から取得されます。 (例外が1つあります。 bot が独自のサインインエクスペリエンスを実装している場合、サインイン UI には users& # 39 が表示されます。IP アドレスと参照情報。)</li><li>メッセージングの拡張機能: 一方で、users& # 39 を参照してください。IP アドレスと参照元情報。</li><li>アプリのガイドライン (およびその AppSource review プロセス) では、正当な目的のために、ユーザーに (POST_MESSAGE_TEAM のアクセス許可を通じて) 個人のチャットメッセージを投稿することが必要です。 不正使用の場合は、ユーザーがボットをブロックできるため、テナント管理者はアプリをブロックすることができます。また、必要に応じて、ボットを一元的にブロックすることができます。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">一部のボットは、メッセージを送信します (POST_MESSAGE_USER)。 They& # 39; 通知のみ&quot;&quot;のボットと呼ばれますが、doesn& # 39; t はボットが許可されているか、許可されていないかを示しています。これは、bot doesn& # 39; t が会話のエクスペリエンスを公開しようとしていることを意味します。 このフィールドは、通常は有効になる UI の機能を無効にするために使用されます。ボット isn& # 39; s は、会話体験を公開するボットと比較して、it& # 39; s に制限されています。</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">現時点では、開発者プレビューです。</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">アプリの manifest.xml <code>supportsFiles</code>ファイルの bot オブジェクトのブール型プロパティによって制御されます。</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>ボットに独自のサインインがある場合は、ユーザーが初めてサインインするときに、2つの方法があります。</li><li>現時点では、Teams アプリ内のいずれかの機能に関連付けられた Azure AD 権限 (ボット、タブ、コネクタ、またはメッセージング拡張機能) は、ここに記載されている Teams の権限から完全に分離されます。</li></ul>


## <a name="tabs"></a>タブ

タブは、Teams 内で実行されている web サイトです。

<table>
  <tr>
    <th width="25%">必要なアクセス許可</th>
    <th width="25%">オプションの権限</th>
    <th width="50%">考慮事項</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">なし (現在)</td>
    <td valign="top"><ul><li>タブのリスクプロファイルは、ブラウザータブで実行されている同じ web サイトとほぼ同じです。 </li><li>また、タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、その場所にある Office 365 グループの ID (チームの場合) など、it& # 39 が実行されているコンテキストが取得されます。、テナント ID、ユーザーの現在のロケール。 ただし、これらの Id を user& # 39; s の情報にマッピングするには、ユーザーが Azure AD にサインインする必要があります。</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>コネクタ

外部システムのイベントが発生すると、コネクタはチャネルにメッセージを投稿します。

  <table>
  <tr>
    <th width="25%">必要なアクセス許可</th>
    <th width="25%">オプションの権限</th>
    <th width="50%">考慮事項</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. 一部のコネクタは、操作可能な<em>メッセージ</em>をサポートします。これにより、ユーザーは GitHub の問題への応答の追加や、Trello カードへの日付の追加などを行うことができます。</td>
    <td valign="top"><ul><li>コネクタメッセージの投稿先のシステムは、doesn& # 39; s さん、またはメッセージを受信したユーザー it& # 39;。受信者に関する情報は開示されません。 (Microsoft は、テナントではなく実際の受信者です。Microsoft はチャネルに実際に投稿します。)</li><li>コネクタメッセージがチャネルに投稿されると、データは企業ネットワークから脱退します。</li><li>操作可能なメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートするコネクタは、don& # 39、「IP アドレスと参照情報」を参照してください。この情報は、Microsoft に送信され、connector ポータルで Microsoft に以前登録されていた HTTP エンドポイントにルーティングされます。</li><li>チャネル用にコネクタを構成するたびに、そのコネクタインスタンスの一意の URL が作成されます。 このコネクタインスタンスが削除されると、URL を使用できなくなります。</li><li>コネクタメッセージ can& # 39、t 添付ファイルが含まれています。</li><li>コネクタインスタンス URL は、秘密/機密として扱う必要があります。この URL は、メールアドレスなど、その URL を持つすべてのユーザーが投稿できます。 したがって、there& # 39 では、スパムやフィッシングサイトへのリンクのリスクが発生する可能性があります。 この問題が発生した場合は、チーム所有者がコネクタインスタンスを削除することができます。</li><li>コネクタメッセージを送信するサービスが侵害され、スパム/フィッシングまたはマルウェアリンクの送信を開始した場合、テナント管理者は、新しいコネクタインスタンスが作成されないようにして、Microsoft がそれらを中央でブロックすることができます。</li></ul></td>
  </tr>
</table>

> [!Note]
> 現在、操作できるメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートしているコネクタを特定することはできません。


## <a name="outgoing-webhooks"></a>発信 web フック

テナントに対してサイドローディングが有効になっている場合、_送信 web フック_は、チーム所有者またはチームメンバーがその場で作成します。 チームアプリの機能ではありません。この情報は、完全性のために含まれています。

<table>
  <tr>
    <th width="25%">必要なアクセス許可</th>
    <th width="25%">オプションの権限</th>
    <th width="50%">考慮事項</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. ユーザーからのメッセージを受信して返信することができます。</td>
    <td valign="top">なし</td>
    <td valign="top"><ul><li>発信 web フックはボットに似ていますが、権限が少なくなっています。 ボットと同じように、明示的にメンションする必要があります。</li><li>送信 webhook が登録されると、<em>秘密</em>が生成されます。これにより、送信の webhook は、悪意のある攻撃者とは異なり、送信者が Microsoft Teams であることを確認できます。 このシークレットは、秘密のままにしておく必要があります。このアプリにアクセスできるすべてのユーザーが、Microsoft Teams を偽装できます。 秘密が侵害された場合は、送信された webhook を削除して再作成することができます。これにより、新しいシークレットが生成されます。</li><li>It& # 39 では、doesn& # 39、秘密を検証する送信 webhook を作成できますが、そのためのことをお勧めします。</li><li>メッセージの受信と返信以外の発信用の webhooks can& # 39; t: これらは、can& # 39; t さんがメッセージを事前に送信し、ファイルを送信または受信できるようにします。それらは、受信と返信以外のボットが実行できるその他の操作を実行します。メール.</li></ul></td>
  </tr>
</table>
