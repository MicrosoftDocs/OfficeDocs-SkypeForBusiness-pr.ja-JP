---
title: 'Lync Server 2013: 集中ログサービスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1c382151d34751e7e934f15fdd2855ce696e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520834"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 の集中ログサービスの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

集中ログサービスは、データの管理されたコレクションのための手段を提供するように設計されています。範囲は広くまたは狭くなっています。 展開内のすべてのサーバーからデータを同時に収集し、トレースする特定の要素を定義し、トレースフラグを設定し、単一のコンピューターまたはすべてのサーバーからのすべてのデータの集約から検索結果を返すことができます。 集中ログサービスは、展開内のすべてのサーバー上で実行されます。 集中ログサービスのアーキテクチャは、次のエージェントとサービスで構成されています。

  - *集中ログサービスエージェント*    ClsAgent.exe は、コントローラーと通信し、管理者によってコントローラーによって発行されたコマンドを受信するサービス実行可能ファイルです。 エージェントは、各 Lync Server コンピュータでサービスとして実行されます。 エージェントは、コマンドを受け取ると、そのコマンドを実行し、トレース用に定義されたコンポーネントにメッセージを送信して、トレースログをディスクに書き込みます。 また、そのコンピューターのトレースログを読み取り、要求されたときにトレースデータをコントローラーに送り返します。 ClsAgent は、 **tcp 50001**、 **Tcp 50002**、 **tcp 50003**の各ポートでコマンドをリッスンします。

  - *集中ログサービスコントローラー*    ClsControllerLib.dll は、Lync Server 管理シェルおよび ClsController.exe のコマンド実行エンジンです。 CLSControllerLib.dll は、開始、停止、フラッシュ、および検索コマンドを ClsAgent に送信します。 検索コマンドが送信されると、結果のログが ClsControllerLib.dll に返され、集約されます。 コントローラーは、エージェントにコマンドを送信し、それらのコマンドの状態を受信し、検索ログファイルのデータを検索範囲内の任意のコンピューターにあるすべてのエージェントから返されたデータを収集し、ログデータを意味のある順序付けられた出力セットに集約する役割を担います。 以下のトピックの情報は、Lync Server 管理シェルを使用することに重点を置いています。 ClsController.exe は、Lync Server 管理シェルで使用可能な機能のサブセットに限定されます。 ClsController.exe のヘルプは、コマンドラインで、 `ClsController` 既定のディレクトリ C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 clsagent を入力することで使用でき \\ ます。

**ClsController と Clscontroller との通信**

![CLSController と Clscontroller との関係。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController と Clscontroller との関係。")

コマンドを実行するには、Windows Server コマンドラインインターフェイスを使用するか、Lync Server 管理シェルを使用します。 コマンドは、ログインしているコンピューター上で実行され、ローカルで、または展開内の他のコンピューターとプールに送信されます。

ClsAgent は、すべてののインデックスファイルを保持します。ローカルコンピューターにあるキャッシュファイル。 ClsAgent は、オプション CacheFileLocalFolders によって定義されたボリューム間で均等に分散されるように割り当て、各ボリュームの80% を消費しないようにします (つまり、ローカルキャッシュの場所とパーセンテージは、 **Set-CsClsConfiguration** コマンドレットを使用して構成できます)。 ClsAgent は、ローカルコンピューターからの古いキャッシュされたイベントトレースログ (.etl) ファイルのエージングも担います。 2週間後 (つまり、 **設定-CsClsConfiguration** コマンドレットを使用してタイムラインを構成できます)、これらのファイルはファイル共有にコピーされ、ローカルコンピューターから削除されます。 詳細については、「 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)」を参照してください。 検索要求を受信すると、検索条件を使用して、キャッシュされた .etl ファイルのセットを選択し、エージェントが管理するインデックスの値に基づいて検索を実行します。

<div>


> [!NOTE]  
> ローカルコンピューターからファイル共有に移動されたファイルは、ClsAgent で検索できます。 ClsAgent がファイルをファイル共有に移動すると、ファイルのエージングと削除は ClsAgent によって維持されません。 ファイル共有内のファイルのサイズを監視し、それらを削除またはアーカイブする管理タスクを定義する必要があります。



</div>

生成されたログファイルは、 **Snooper.exe** や、 **Notepad.exe**などのテキストファイルを読み取ることができるツールなど、さまざまなツールを使用して読み取りおよび分析できます。 Snooper.exe は Lync Server 2013 デバッグツールに含まれており、Web からダウンロードでき [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) ます。

OCSLogger と同様に、集中ログサービスには追跡するコンポーネントがいくつかあり、TF コンポーネントや TF DIAG などのフラグを選択するためのオプションが提供されてい \_ \_ ます。 集中ログサービスでは、OCSLogger のログレベルのオプションも保持されます。

コマンドラインの ClsController で Lync Server 管理シェルを使用する場合の最も重要な利点は、選択されたプロバイダーを使用して、問題の領域、カスタムフラグ、およびログ出力レベルを対象とする新しいシナリオを構成および定義できることです。 ClsController で使用できるシナリオは、実行可能ファイルに対して定義されているものに限られます。

以前のバージョンでは、管理者とサポート担当者が展開内のコンピューターからトレースファイルを収集できるようにするために OCSLogger.exe が提供されていました。 OCSLogger には、すべての長所を使用した欠点がありました。 ログは、一度に1台のコンピューターでのみ収集できます。 OCSLogger の別のコピーを使用して複数のコンピューターにログオンすることはできますが、最終的には複数のログが作成され、結果を集約する簡単な方法はありません。

ユーザーがログ検索を要求すると、ClsController は (選択されたシナリオに基づいて) 要求を送信するコンピューターを決定します。 また、保存された .etl ファイルが配置されているファイル共有に検索を送信する必要があるかどうかを判断します。 検索結果が ClsController に返されると、コントローラーは結果を、ユーザーに提示される1つの時間を指定した結果セットに結合します。 ユーザーは、検索結果をローカルコンピューターに保存して、詳細な分析を行うことができます。

ログセッションを開始するときは、解決しようとしている問題に関連するシナリオを指定します。 いつでも2つのシナリオを実行できます。 これら2つのシナリオのいずれか1つは、AlwaysOn シナリオにする必要があります。 その名前が示すように、その名前が展開で常に実行されており、すべてのコンピューター、プール、およびコンポーネントに関する情報が収集されている必要があります。

<div>


> [!IMPORTANT]  
> 既定では、AlwaysOn シナリオは展開で実行されていません。 シナリオを明示的に開始する必要があります。 開始すると、明示的に停止するまで実行が続行され、コンピューターの再起動によって実行状態が維持されます。 シナリオの開始および停止の詳細については、「 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for The Lync server 2013」</A> および「 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using Stop For the lync server 2013</A>」を参照してください。



</div>

問題が発生した場合は、報告された問題に関連する2番目のシナリオを開始します。 問題を再現し、2番目のシナリオのログ記録を停止します。 報告された問題に対して、ログの検索を開始します。 集約されたログのコレクションによって、展開のサイト内またはグローバルスコープ内のすべてのコンピューターからのトレースメッセージを含むログファイルが生成されます。 検索によってより多くのデータが返された場合は、可能 analyze (通常は、雑音が多すぎるという信号対雑音比) では、パラメーターを狭くしてもう一度検索を実行します。 この時点で、表示されているパターンを開始することができ、問題により明確に焦点を当てるのに役立ちます。 最終的には、いくつかの改良された検索を実行した後、問題に関連するデータを見つけて、根本原因を特定することができます。

<div>


> [!TIP]  
> Lync Server で問題のシナリオが表示されたら、「問題について既に知っていることは何ですか」という質問をして始めます。 問題の境界を定量化すると、Lync Server の運用エンティティの大部分をなくすことができます。<BR>ユーザーが連絡先を検索するときに現在の結果を取得していないことがわかっているシナリオ例を考えてみます。 メディアコンポーネント、エンタープライズ Voip、会議、その他の多くのコンポーネントの問題を探すポイントはありません。 実際に問題が発生しているのは、クライアントで、またはサーバー側の問題であることが不明な場合があります。 連絡先は、ユーザーレプリケーターによって Active Directory から収集され、アドレス帳サーバー (ABServer) を介してクライアントに配信されます。 ABServer は、(ユーザーレプリケーターが書き込んだ) RTC データベースから更新を取得し、アドレス帳ファイルに収集します (既定では、1:30 AM)。 Lync Server クライアントは、ランダムなスケジュールで新しいアドレス帳を取得します。 プロセスがどのように機能するかがわかっているので、ユーザーレプリケーターによって Active Directory から収集されたデータに関連する問題、またはアドレス帳ファイルを取得したり作成したりしていない、またはアドレス帳ファイルをダウンロードしていないクライアントで、発生する可能性のある検索を減らすことができます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

