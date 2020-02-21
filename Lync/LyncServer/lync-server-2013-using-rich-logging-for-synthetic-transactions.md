---
title: 'Lync Server 2013: 代理トランザクションに対してリッチログを使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 で代理トランザクションに対してリッチログを使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

代理トランザクション (Microsoft Lync Server 2010 で導入されたもの) は、管理者が、システムへのログオン、インスタントメッセージの交換、または特定の電話への通話の作成などの一般的なタスクを、ユーザーが正常に完了できたことを確認する方法を提供します。公衆交換電話網 (PSTN)。 これらのテスト (Lync Server Windows PowerShell コマンドレットのセットとしてパッケージ化されたもの) は、管理者によって手動で実行することも、System Center Operations Manager などのアプリケーションによって自動的に実行することもできます。

Lync Server 2010 では、代理トランザクションは、システムの問題を特定するために管理者を支援するために非常に役立つことが実証されています。 たとえば、 **Test-CsRegistration**コマンドレットを使用すると、一部のユーザーが Lync Server に登録するのに困難があるという事実を管理者に通知できます。 ただし、代理トランザクションは、管理者が Lync Server への登録を困難にした理由を判断するのに役立ちます。 これは、代理トランザクションが Lync Server の問題のトラブルシューティングに役立つ可能性がある詳細なログ情報を提供していないためです。 せいぜい、代理トランザクションからの詳細出力では、問題がどこで発生したかを管理者が推測できる、ステップごとの情報を示すだけでした。

Microsoft Lync Server 2013 では、代理トランザクションは、リッチログを提供するように再設計されています。 "高機能なログ記録" とは、代理トランザクションが行う各アクティビティについて、以下のような情報が記録されるということです。

  - アクティビティが開始した時間

  - アクティビティが終了した時間

  - 実行されたアクション (たとえば、会議の作成、参加、または退室、Lync Server へのサインオン、インスタントメッセージの送信など)

  - アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ

  - SIP 登録メッセージ

  - アクティビティが行われたとき生成された例外レコードまたは診断コード

  - アクティビティを実行した全体的な結果

代理トランザクションが実行されるたびに、この情報は自動的に生成されます。 しかし、この情報は、自動的に表示されることや、ログ ファイルに保存されることはありません。 代わりに、代理トランザクションを手動で実行している管理者は、OutLoggerVariable パラメーターを使用して、情報を格納する Windows PowerShell 変数を指定できます。 次に、管理者は、ペアのメソッドを使用して、リッチ ログを XML または HTML 形式で、保存または表示できます。

たとえば、Lync Server 2010 の管理者は、次のようなコマンドを使用して、 **CsRegistration**コマンドレットを実行することができます。

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

これらのファイルは、Internet Explorer、Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使用して表示できます。

System Center Operations Manager の内部から実行される代理トランザクションは、エラーが発生したときにこれらのログファイルを自動的に生成します。 ただし、これらのログは、Windows PowerShell が代理トランザクションを読み込んで実行できるようになる前に、実行が失敗した場合は生成されません。

> [!IMPORTANT]  
> 既定では、Lync Server 2013 は、共有されていないフォルダーにログファイルを保存します。 このようなログにアクセスできるようにするには、このフォルダーを\\ \\共有する必要があります (例: litwareinc。 com\WatcherNode.


</div>

</div>

</div>

</div>

