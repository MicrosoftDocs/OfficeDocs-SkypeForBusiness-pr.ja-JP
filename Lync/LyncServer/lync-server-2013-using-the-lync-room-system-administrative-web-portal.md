---
title: 'Lync Server 2013: Lync Room System Administrative Web Portal の使用'
TOCTitle: Lync Room System Administrative Web Portal の使用
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62269002
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync Room System Administrative Web Portal の使用

 

_**トピックの最終更新日:** 2014-11-10_

サーバーで LRS を展開した後、ブラウザーから LRS Administrative Web Portal にサインインして、すべての LRS ルームの状態を確認できます。

## サインイン

1.  次の URL に移動します。
    
    https://\<fe-server\>/lrs

2.  LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されているアカウントを入力します。

![Lync Room System、管理用ポータル サインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System、管理用ポータル サインイン画面")

## \[LRS Administrative Web Portal の概要\] ページ

この概要ページには、サーバーで展開されたすべての LRS ルームに関する次の情報が表示されます。

  - **タグ**   管理者がルームに指定する名前です。ルーム名をクリックすると、ポータルでタグを設定できます。

  - **動作状態**   ルームの動作状態です。これは、ルームの \[動作状態集計\] の状態から派生し、\[ルーム設定\] ページの \[動作状態\] セクションの下に表示されます。

  - **次の会議**   次の会議がスケジュールされている日時です。

  - **LRS バージョン、製造元、モデル**   これらの値は LRS で事前に設定されています。製造元に応じて、これらのフィールドは空白のままである場合があります。

  - **最終更新**   Web ページが最後に更新された時刻が表示されます。

![Lync Room System、管理用ポータル概要ビュー](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System、管理用ポータル概要ビュー")

## LRS ルーム情報

ポータルの \[ルーム情報\] セクションでは、個々の LRS ルームを表示および構成することができます。これには、\[設定\]、\[詳細\]、\[ログ記録\]、\[動作状態\] の 4 つのセクションがあります。

## 設定

\[設定\] セクションでは、パスワード、ルーム タグ、ルームの既定のボリューム レベルを設定できます。これらの設定を構成すると、LRS コンソールを再起動した後に、変更がレプリケートされます。

![Lync Room System、管理用ポータル ルームの設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System、管理用ポータル ルームの設定")

## 詳細

\[詳細\] セクションには、LRS ルームの設定の読み取り専用の概要 (最終更新の時刻、次の会議、最終更新、メンテナンスと調整、既定のスピーカー、マイク、呼び出しの設定、バージョン、SIP URI、スクリーン数、各スクリーンの詳細、状態、アクティビティなど) が表示されます。

![Lync Room System、管理用ポータル詳細ビュー](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System、管理用ポータル詳細ビュー")

## ログ記録

\[ログ記録\] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。また、LRS コンソール (LRS ユーザー インターフェイス) を再起動したり、システム全体を再起動したりすることもできます。

![Lync Room System、管理用ポータル ルームのログ](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System、管理用ポータル ルームのログ")

## Health (動作状態)

\[Health (動作状態)\] セクションでは、Lync Server 接続、オーディオ デバイス、ビデオ デバイス、復元の状態、およびスクリーン デバイスの動作状態が表示されます。

![Lync Room System、管理用ポータル ルームの正常性](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System、管理用ポータル ルームの正常性")

## LRS Administrative Web Portal に関する追加の注意事項

> [!NOTE]  
> <ul><li><p>セキュリティ上の理由から、LRS Administrative Web Portal では、自動的に 15 分ごとにサインアウトされます。</p></li>
> <li><p>設定の変更は、LRS システムが再起動した後に適用されます。</p></li>
> <li><p>LRS Administrative Web Portal での通知は継続的なものです。つまり、通知は非表示になりません。</p></li>
> <li><p>通知は、ページを更新した後に表示されます。</p></li>
> <li><p>LRS ルームの状態は、ページを更新した後に表示されます。</p></li>
> <li><p>LRSApp アカウントのパスワードが期限切れになると、ルームの状態を確認できなくなります。有効期限が切れないように LRSAppuser アカウントのパスワードを構成するか、有効期限が近づいたらそのパスワードを更新してください。</p></li>
> <li><p>LRS Administrative Web Portal は、内部設置型展開でのみサポートされます。</p></li></ul>


## トラブルシューティング

## LRS Administrative Web Portal にサインインできないのはなぜですか。

  - https://localhost/lrs を開くと、サインイン ページが表示されますが、資格情報を入力してもサインインできません。この場合は、https://FQDNofFEserver/lrs を開いて LRS Administrative Web Portal にサインインする必要があります。

  - LRS Administrative Web Portal へのアクセスに使用するコンピューターがワークグループに属する場合、"http://" を使用できません。代わりに、"https" を使用してください。

## LRS Administrative Web Portal で LRS を表示できないのはなぜですか。

  - 展開で LRS アカウントを取得していること、それらのアカウントが LRS Administrative Web Portal 展開の推奨事項に従って作成されていることを確認してください。さらに、Enable-CsUser でなく、Enable-CsMeetingRoom を使用して Lync サーバーで LRS アカウントがプロビジョニングされていることを確認してください。

  - LRS アカウントを作成しても、LRS Administrative Web Portal でそのアカウントを確認できない場合は、**MeetingPortal** コンポーネントを選択した状態で Lync Server ログ ツールを使用してサーバー ログを収集してから、そのログを LRS サポートの連絡先に送信してください。

## LRS Administrative Web Portal で LRS の状態を確認できないのはなぜですか。

  - LRSApp ユーザー アカウントが SIP 対応であることを確認してください。

  - それでも問題がある場合は、D:\\Tracing\\LRSAdminLogs\\ から LRS システムの **Trace.log** ファイルを収集してから、そのファイルを LRS サポートの連絡先に送信してください。

