---
title: 'Lync Server 2013: 代理トランザクションでのリッチログの使用'
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
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 での代理トランザクションに対するリッチログの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

代理トランザクション (Microsoft Lync Server 2010 で導入されました) では、管理者は、システムへのログオン、インスタントメッセージの交換、または特定の電話への通話の発信などの一般的なタスクを正常に完了できることを管理者が確認する方法を提供します。[公衆交換電話網 (PSTN)] を選びます。 これらのテスト (Lync Server Windows PowerShell コマンドレットのセットとしてパッケージ化されているもの) は、管理者によって手動で実行することも、System Center Operations Manager などのアプリケーションで自動的に実行することもできます。

Lync Server 2010 では、管理者がシステムの問題を特定するのに役立つように、代理トランザクションが非常に役立ちます。 たとえば、 **CsRegistration**コマンドレットを使用すると、一部のユーザーが Lync Server への登録に障碍があることを管理者に通知することができます。 ただし、代理トランザクションは、管理者が Lync Server に登録できない理由を特定するのに役立ちます。 これは、管理者が Lync Server の問題のトラブルシューティングを行うときに役立つ詳細なログ情報が、代理トランザクションによって提供されなかったことが原因です。 最善策として、合成トランザクションからの冗長な出力について説明しました。管理者は、問題が発生した可能性のある箇所についての知識を得ることができる場合があります。

Microsoft Lync Server 2013 では、リッチなログを提供するために、代理トランザクションが再設計されています。 "リッチログ" とは、代理トランザクション請け負うの各アクティビティについて、次のような情報が記録されることを意味します。

  - アクティビティが開始された時刻

  - アクティビティが完了した時刻

  - 実行されたアクション (たとえば、会議の作成、参加、退席、Lync サーバーへのサインイン、インスタントメッセージの送信など)

  - アクティビティが行われたときに生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ

  - SIP 登録メッセージ

  - アクティビティの実行時に生成される例外レコードまたは診断コード

  - アクティビティを実行した場合の最終的な結果

この情報は、代理トランザクションが実行されるたびに自動的に生成されます。 ただし、情報が自動的に表示されたり、ログファイルに保存されたりすることはありません。 代わりに、代理トランザクションを手動で実行している管理者は、OutLoggerVariable パラメーターを使って、情報が格納される Windows PowerShell 変数を指定できます。 このような場合、管理者は、XML 形式または HTML 形式のリッチログの保存や表示を行うことができるようにする一連のメソッドを使うことができます。

たとえば、Lync Server 2010 管理者は、次のようなコマンドを使用して、 **CsRegistration**コマンドレットを実行することができます。

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

管理者には、OutLoggerVariable パラメーターと、その後に選択する変数名を含めるオプションがあります。

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 変数名の先頭に $ 文字を付けないでください。 RegistrationTest などの変数名を使用しますが、$RegistrationTest は使用しないでください。

上のコマンドを実行すると、次のような内容が出力されます。

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

ただし、このエラーには、上に示したエラーメッセージだけでなく、さらに詳細な情報が記載されています。 HTML 形式でその情報にアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に保存されている情報を HTML ファイルに保存します。

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

これらのファイルは、Internet Explorer、Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使って表示できます。

System Center Operations Manager の内部で実行される代理トランザクションでは、エラーのログファイルが自動的に生成されます。 ただし、Windows PowerShell が代理トランザクションを読み込んで実行できない場合は、これらのログは生成されません。

> [!IMPORTANT]  
> 既定では、Lync Server 2013 は共有されていないフォルダーにログファイルを保存します。 これらのログにアクセスできるようにするには、このフォルダーを共有\\ \\する必要があります (例: litwareinc com\WatcherNode.


</div>

</div>

</div>

</div>

