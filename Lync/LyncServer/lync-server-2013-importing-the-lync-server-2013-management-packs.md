---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Lync Server 2013 管理パックのインポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

管理パック (System Center Operations Manager が監視できる項目を決定するソフトウェア、およびそれらの項目を監視する方法、およびアラートをトリガーする方法、および警告をトリガーする方法) をインストールすることによって System Center Operations Manager の機能を拡張することができます。発生. Lync Server 2013 には、次の機能を提供する System Center Operations Manager の2つの管理パックが含まれています。

  - コンポーネントとユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話の詳細レコード (CDR) またはエクスペリエンスの品質 (QoE) に記録します。databases. 重大な問題については、System Center Operations Manager を構成して、メール、インスタントメッセージ、またはショートメッセージサービス (SMS) メッセージングを使って管理者にすぐに通知することができます。 SMS は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。)
    
    <div>
    

    > [!NOTE]  
    > Operations Manager の通知の構成の詳細については、TechNet ライブラリの「 <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>通知を設定する」を参照してください。

    
    </div>

  - アクティブな監視管理パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタントメッセージの交換、パブリックスイッチのある電話への呼び出しなど、Lync Server の主要なコンポーネントを事前にテストします。電話網 (PSTN)。 これらのテストは、Lync Server の代理トランザクションコマンドレットを使用して行われます。 たとえば、テスト**用の cgi**コマンドレットを使用して、1組のテストユーザー間のインスタントメッセージング (IM) 会話をシミュレートできます。 このシミュレートされたメッセージの会話に失敗した場合は、アラートが生成されます。

管理パックをインポートする必要があります。 管理パックをインポートしない場合、Operations Manager を使用して Lync Server イベントを監視したり、Lync Server の代理トランザクションを実行したりすることはできません。

コンポーネントとユーザー管理パックは、Lync Server 2013 を監視するためだけに使用されます。 Lync Server 2013 と Lync Server 2010 の両方がインストールされている共存シナリオを使用している場合は、引き続き lync server 2010 コンピューター用の Lync Server 2010 管理パックを使用する必要があります。

<div>


> [!NOTE]  
> Lync server 2010 用の管理パックには、Lync Server 2010 監視管理パックと Lync Server 2010 グループチャット監視管理パックが含まれています。



</div>

次のいずれかのツールを使用して、管理パックをインポートできます。

  - **System Center Operations manager**   この方法では、Operations manager を使用して Lync Server の監視を追加します。

  - **Operations manager shell**   operations manager shell を使用して直接インポートするか、System Center Operations Manager コンソールを使用して、管理パックのインポート時に発生した問題のトラブルシューティングを行うことができます。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1.  Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルをダウンロードします。

2.  System Center Operations Manager で、[**管理**] をクリックします。

3.  [管理**** ] ウィンドウで、[**管理パック**] を右クリックし、[**管理パックのインポート**] をクリックします。

4.  [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5.  [**オンラインカタログ接続**] ダイアログボックスで、[**キャンセル**] をクリックして、Lync Server 管理パックの依存関係が存在するかどうかを確認します。 System Center Operations Manager 2012 を使っている場合は、[**いいえ**] をクリックします。

6.  **[インポートする管理パックの選択**] ダイアログボックスで、 **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp**と**Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**ファイルを探して選び、[**開く**] をクリックします。 ダイアログボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら2番目のファイルをクリックします。

7.  [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。 エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。 この問題が発生した場合は、ファイルを別のフォルダーにコピーし、インポートとインストールのプロセスを再起動します。

8.  [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。 インポートとインストールのプロセスには数分かかる場合があることに注意してください。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用して管理パックをインポートする

通常、管理パックのインポートは、Operations Manager を使用して簡単に行うことができます。ただし、エラーが発生してインポートが失敗した場合は、コンソールが適切なエラーレポートを提供するとは限りません。 比較では、Operations Manager Shell に詳細情報が表示されます。 Operations Manager を使用していて、管理パックのインポートで問題が発生した場合は、Operations Manager Shell を使用してパックをインポートします。 Operations Manager Shell には、インポートが失敗した理由を特定するのに役立つ情報が記載されています。

System Center Operations Manager 2007 R2 を使用している場合は、次の手順を実行します。

1.  [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **System Center Operations Manager 2007 R2**] をクリックして、[ **Operations Manager Shell**] をクリックします。

2.  Operations Manager シェルで、コマンドプロンプトで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルの実際のパスを使用して、次のコマンドを入力し、ENTER キーを押します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーへのパスを使用して、次の手順を繰り返します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Operations Manager シェルを閉じます。

System Center Operations Manager 2012 を使用している場合は、代わりに次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[**Microsoft System Center 2012**]、[**Operations Manager**] の順にクリックし、[**Operations Manager シェル**] をクリックします。

2.  Operations Manager シェルで、コマンドプロンプトで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルの実際のパスを使用して、次のコマンドを入力し、ENTER キーを押します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーへのパスを使用して、次の手順を繰り返します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

