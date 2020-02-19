---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 759cae91575d3244d6860c6ec76fa664994d493e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Lync Server 2013 での Lync Room System 管理 Web ポータルの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-10_

サーバーに LRS を展開した後、ブラウザーから LRS 管理 Web ポータルにサインインして、すべての LRS ルームの状態を確認できます。

<div>

## <a name="sign-in"></a>サインイン

1.  次の URL を参照します。
    
    https://\<fe-サーバー\>/lrs

2.  LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティグループに追加されているアカウントを入力します。

![Lync Room System 管理者ポータルのサインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System 管理者ポータルのサインイン画面")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 管理 Web ポータルの概要ページ

概要ページには、サーバーに展開されているすべての LRS ルームに関する次の情報が表示されます。

  - **タグ**   管理者がルームに付与するカスタム名を指定します。 タグは、ルーム名をクリックすることで、ポータルで設定できます。

  - **[正常性**   ] 会議室の正常性の状態を示します。これは、会議室の設定ページの [正常性] セクションに表示されます。

  - **[次の会議**   ] 次の会議がスケジュールされた日時です。

  - **LRS Version, Manufacturer, Model**   これらの値は、LRS で事前に設定されています。 製造元によっては、これらのフィールドが空白のままになっている場合があります。

  - **最終更新**   web ページが最後に更新された日時が表示されます。

![Lync Room System 管理ポータルの概要ビュー](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System 管理ポータルの概要ビュー")

</div>

<div>

## <a name="lrs-room-information"></a>LRS ルーム情報

ポータルの [Room Info] セクションでは、個々の LRS ルームを表示および構成できます。 これには、[設定]、[詳細]、[トラブルシューティング]、[正常性] の4つのセクションがあります。

<div>

## <a name="settings"></a>設定

[設定] セクションでは、ルームのパスワード、会議室タグ、および既定の音量レベルを設定できます。 これらの設定を構成すると、LRS コンソールを再起動した後にのみ変更がレプリケートされます。 Lync Room システムでは、バージョン15.12 以降のシステム更新設定のみが表示されます。

![Lync Room System 管理ポータルルームの設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System 管理ポータルルームの設定")

</div>

<div>

## <a name="details"></a>詳細

[詳細] セクションには、LRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新日時が含まれます。次の会議。最終更新、メンテナンス、調整、既定のスピーカー、マイク、および着信音の設定。4.0SIP URI。画面の数と各画面の詳細。状態、およびアクティビティ。

![Lync Room System 管理ポータル詳細ビュー](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System 管理ポータル詳細ビュー")

</div>

<div>

## <a name="troubleshooting"></a>トラブルシューティング

トラブルシューティングのセクションは、ログをリモートで収集し、指定した場所に保存するために使用できます。 LRS コンソール (LRS ユーザーインターフェイス) を再起動したり、システム全体を再起動したりすることもできます。 ログを収集するには、指定された形式のフォルダーパスを指定し、LRS コンピューターアカウントに指定された書き込み権限がフォルダーにあることを確認します。 ログサイズが大きすぎる場合は、ログの収集が完了するまでに最大5分かかる場合があります。 ページを更新すると、最新の状態が表示されます。

![Lync Room System 管理ポータルルームのログ記録](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System 管理ポータルルームのログ記録")

</div>

<div>

## <a name="health"></a>正常性

[正常性] セクションは、Lync Server の接続、オーディオデバイス、ビデオデバイス、復元状態、および画面デバイスの正常性を視覚的に示します。

![Lync Room System 管理ポータルルームの正常性](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System 管理ポータルルームの正常性")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web ポータルに関するその他の注意事項

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>設定変更は、LRS システムが再起動された後にのみ適用されます。</P>
> <LI>
> <P>LRSApp アカウントのパスワードが期限切れになると、ルームの状態を表示することはできません。 LRSAppuser アカウントのパスワードを有効期限切れにならないように構成するか、有効期限が近づいたときにパスワードを更新してください。</P>
> <LI>
> <P>LRS 管理 web ポータルは、オンプレミスの展開でのみサポートされています。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>よく寄せられる質問

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>管理 web ポータルにサインインできないのはなぜですか?

  - を開くhttps://localhost/lrsと、サインインページを表示できるようになりますが、サインイン情報を入力するときにサインインすることはできません。 この場合は、を開いhttps://FQDNofFEserver/lrsて、管理 web ポータルにサインインする必要があります。

  - 管理 web ポータルにアクセスするコンピューターがワークグループ内にある場合、"http://" は機能しません。 代わりに "https" を使用します。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>管理 web ポータルで LRS が表示されないのはなぜですか?

  - 展開に LRS アカウントがあること、および LRS 管理 Web ポータルの展開に関する推奨事項に従って作成されていることを確認してください。 Lync server で、LRS アカウントが、[有効-CsUser] ではなく [Enable-Csの会議室] を使用してプロビジョニングされていることを確認してください。

  - LRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されていない場合は、「Lync Server Logging tool を使用して**会議ポータル**コンポーネントを選択して、サーバーログを収集し、それらを LRS サポート連絡先に送信します。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>管理 web ポータルで LRS の状態を確認できないのはなぜですか?

  - LRSApp ユーザーアカウントの SIP が有効になっていることを確認します。

  - それでも問題が解決しない場合は、D:\\Tracing\\lrsadminlogs\\から LRS システムの**TRACE .log**ファイルを収集し、LRS サポート連絡先に送信します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

