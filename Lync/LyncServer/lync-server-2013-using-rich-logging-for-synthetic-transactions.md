---
title: 代理トランザクションのリッチ ログの使用
TOCTitle: 代理トランザクションのリッチ ログの使用
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48271683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 代理トランザクションのリッチ ログの使用

 

_**トピックの最終更新日:** 2012-10-22_

Microsoft Lync Server 2010 で導入された代理トランザクションにより、管理者は、システムへのログオン、インスタント メッセージの交換、公衆交換電話網 (PSTN) 上の電話への発信などの一般的なタスクをユーザーが正常に実行できることを検証するものです。これらのテストは、一連の Lync ServerWindows PowerShell コマンドレットとしてパッケージ化されており、管理者が手動で実行することも、System Center Operations Manager などのアプリケーションから自動で実行することもできます。

Lync Server 2010 で、代理トランザクションは、管理者がシステムの問題を識別する際に非常に役立っていました。たとえば、**Test-CsRegistration** コマンドレットは、一部のユーザーの Lync Server への登録がうまくいっていないことを管理者に通知できました。しかし、代理トランザクションは、管理者が、これらのユーザーの Lync Server への登録で問題が発生していた原因を判定することにはあまり役立ちませんでした。これは、代理トランザクションでは、管理者が Lync Server での問題をトラブルシューティングできる詳細なログ記録情報が提供されなかったことによります。せいぜい、代理トランザクションからの詳細出力では、問題がどこで発生したかを管理者が推測できる、ステップごとの情報を示すだけでした。

Microsoft Lync Server 2013では、代理トランザクションは、高機能なログ記録を実現するよう再設計されました。"高機能なログ記録" とは、代理トランザクションが行う各アクティビティについて、以下のような情報が記録されるということです。

  - アクティビティが開始した時間

  - アクティビティが終了した時間

  - 実行されたアクション (たとえば、電話会議の作成、参加、または終了、Lync Server へのサインオン、インスタント メッセージの送信など)

  - アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ

  - SIP 登録メッセージ

  - アクティビティが行われたとき生成された例外レコードまたは診断コード

  - アクティビティを実行した全体的な結果

代理トランザクションが実行されるたびに、この情報は自動的に生成されます。しかし、この情報は、自動的に表示されることや、ログ ファイルに保存されることはありません。この場合、手動で代理トランザクションを実行中の管理者は、OutLoggerVariable パラメーターを使用して、情報が保存された Windows PowerShell 変数を指定できます。次に、管理者は、ペアのメソッドを使用して、リッチ ログを XML または HTML 形式で、保存または表示できます。

たとえば、Lync Server 2010 管理者は、以下のようなコマンドを使用して **Test-CsRegistration** コマンドレットを実行できます。

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

管理者は、OutLoggerVariable パラメーターと、それに続く任意の変数名を含めることができます。

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]
> 変数名の前に $ 記号を付けないでください。$RegistrationTest ではなく、RegistrationTest のような変数名を使用します。


前記のコマンドは、以下のような内容を出力します。

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

実際には、この障害については、上記のエラー メッセージだけでなく、より詳細な情報を参照できます。この情報に HTML 形式でアクセスするには、以下のようなコマンドを使用して、変数 RegistrationTest に保存された情報を HTML ファイルに保存します。

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

これらのファイルは、Internet Explorer、Visual Studio、またはその他すべての HTML/XML ファイルを開けるアプリケーションで表示できます。

System Center Operations Manager の内側から実行された代理トランザクションは、障害が発生した場合、これらのログ ファイルを自動的に生成します。しかし、これらのログは、Windows PowerShell が読み込まれて、代理トランザクションを行う前に、実行が失敗した場合、生成されません。


> [!IMPORTANT]
> 既定で、Lync Server 2013は、共有されていないフォルダーにログ ファイルを保存します。これらのログにすぐにアクセスできるように、このフォルダーを共有する必要があります (たとえば、\\\\atl-watcher-001.litwareinc.com\WatcherNode)。


