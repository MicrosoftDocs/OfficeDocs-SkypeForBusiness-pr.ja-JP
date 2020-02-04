---
title: 'Lync Server 2013: Lync Room System Administrative Web Portal の使用'
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
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Lync Server 2013 での Lync Room System Administrative Web Portal の使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-10_

サーバーに LRS を展開した後は、ブラウザーから LRS 管理 Web ポータルにサインインして、すべての LRS 室の状態を確認できます。

<div>

## <a name="sign-in"></a>サインイン

1.  次の URL を参照します。
    
    https://\<fe-サーバー\>/lrs

2.  LRSSupport アカウントの資格情報または LRSSupportAdminGroup セキュリティグループに追加されたアカウントの資格情報を入力します。

![Lync Room System、管理用ポータル サインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System、管理用ポータル サインイン画面")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 管理 Web ポータルの概要ページ

概要ページには、サーバーに展開されているすべての LRS 室に関する次の情報が表示されます。

  - ****   管理者が会議室に提供したカスタム名をタグ付けします。 ルームの名前をクリックすると、ポータルでタグを設定できます。

  - **正常性**   会議室の正常性の状態を示します。これは、[ルームの設定] ページの [正常性] セクションに表示されます。

  - **次の会議**   次回の会議のスケジュールが設定された日付と時刻。

  - **LRS のバージョン、製造元、モデル**   これらの値は LRS で事前設定されています。 製造元によって、これらのフィールドは空白のままである場合があります。

  - **[最終更新**   日時を表示するには、web ページの最終更新日を表示します。

![Lync Room System、管理用ポータル概要ビュー](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System、管理用ポータル概要ビュー")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 室の情報

ポータルの [ルーム情報] セクションでは、個々の LRS ルームを表示して構成することができます。 これには、[設定]、[詳細]、[トラブルシューティング]、[正常性] の4つのセクションがあります。

<div>

## <a name="settings"></a>設定

[設定] セクションでは、パスワード、ルーム タグ、ルームの既定のボリューム レベルを設定できます。 これらの設定を構成した場合、変更は LRS 本体を再起動した後にのみレプリケートされます。 Lync Room Systems のバージョン15.12 以降のシステム更新設定のみが表示されます。

![Lync Room System、管理用ポータル ルームの設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System、管理用ポータル ルームの設定")

</div>

<div>

## <a name="details"></a>詳細

[詳細] セクションには、LRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新時刻が含まれます。次の会議最終更新、メンテナンス、調整。既定のスピーカー、マイク、着信音の設定バージョンSIP URI画面の数と各画面の詳細。状態、アクティビティ。

![Lync Room System、管理用ポータル詳細ビュー](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System、管理用ポータル詳細ビュー")

</div>

<div>

## <a name="troubleshooting"></a>トラブルシューティング

[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。 LRS console (LRS ユーザーインターフェイス) を再起動するか、システム全体を再起動することもできます。 ログを収集するには、指定した形式のフォルダーパスを指定し、フォルダーに LRS コンピューターアカウントに対する書き込みアクセス許可が与えられていることを確認します。 ログ サイズが大きすぎる場合は、ログの収集を完了するのに最大約 5 分かかる可能性があります。 ページを更新すると、最新の状態が表示されます。

![Lync Room System、管理用ポータル ルームのログ](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System、管理用ポータル ルームのログ")

</div>

<div>

## <a name="health"></a>動作状態

[正常性] セクションには、Lync Server の接続、オーディオデバイス、ビデオデバイス、復元の状態、および画面デバイスの正常性が視覚的に示されます。

![Lync Room System、管理用ポータル ルームの正常性](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System、管理用ポータル ルームの正常性")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web ポータルに関する追加の注意事項

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>設定の変更は、LRS システムを再起動した後にのみ適用されます。</P>
> <LI>
> <P>LRSApp アカウントのパスワードが期限切れになると、ルームの状態を確認できなくなります。 有効期限が切れないように LRSAppuser account のパスワードを構成するか、有効期限が近いときにパスワードを更新してください。</P>
> <LI>
> <P>LRS 管理 web ポータルは、オンプレミスの展開でのみサポートされます。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>よく寄せられる質問

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>管理 Web ポータルにサインインできないのはなぜですか。

  - を開くhttps://localhost/lrsと、サインインページが表示されますが、資格情報を入力するときにサインインすることはできません。 この場合、管理 web ポータルにhttps://FQDNofFEserver/lrsサインインするには、を開く必要があります。

  - 管理 web ポータルにアクセスするコンピューターがワークグループ内にある場合、"http://" は動作しません。 代わりに "https" を使用します。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>管理 web ポータルに LRS が表示されないのはなぜですか?

  - LRS アカウントが展開に含まれていること、および LRS 管理 Web ポータルの展開に関する推奨事項に従って作成されていることを確認します。 Lync server で、LRS のアカウントが、ユーザーを有効にすることなく、Csroom room を使用してプロビジョニングされていることを確認します。

  - LRS アカウントを作成していて、管理 web ポータルにアカウントが表示されない場合は、Lync Server ログツールを使って、**会議ポータル**コンポーネントが選択されている状態で、サーバーログを収集し、LRS サポート連絡先に送信します。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>管理 web ポータルで LRS の状態が表示されないのはなぜですか?

  - LRSApp ユーザー アカウントが SIP 対応であることを確認してください。

  - それでも問題が解決されない場合は、D:\\Tracing\\LRSADMINLOGS\\から LRS システムの**Trace .LOG**ファイルを収集して、LRS のサポート担当者に送信します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

