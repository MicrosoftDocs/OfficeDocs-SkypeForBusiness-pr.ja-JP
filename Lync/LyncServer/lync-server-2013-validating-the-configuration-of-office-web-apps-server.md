---
title: Office Web Apps サーバーの構成の検証
TOCTitle: Office Web Apps サーバーの構成の検証
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48274157
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Office Web Apps サーバーの構成の検証

 

_**トピックの最終更新日:** 2014-04-22_

Office Web Apps Server がトポロジーに追加され、トポロジーが公開された後、 Lync Server イベント ログに 2 つの新しいイベント ログが表示されます。まず、LS Data MCU イベント (イベント ID 41034) が追加されます。このイベントは、Office Web Apps Server が検出されたことを報告します。

\[**Web 会議サーバー WAC が検出され、PowerPoint コンテンツが有効になりました。**\]

これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。

\[**Web 会議サーバー WAC の検出に成功しました。**\]

**WAC 内部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**WAC 内部参加者ページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**WAC 外部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**WAC 内部参加者ページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。この場合、Microsoft Lync Server 2013 は、新たに構成された Office Web Apps Server を必要であれば何度でも検出しようとします。検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。

Office Web Apps Server が正しく構成されているようで、検出プロセスでも認識される場合、Office Web Apps Server が期待どおりに機能しているかどうかを確認するためには、PowerPoint プレゼンテーションを 2 つの Microsoft Lync 2013 クライアントで共有してみます。ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。

Office Web Apps Server が正しく構成されているような場合でも、PowerPoint プレゼンテーションを共有する際に「サーバーの接続問題により、一部の共有機能が使用できません」というエラー メッセージを受け取ることがあります。このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。

