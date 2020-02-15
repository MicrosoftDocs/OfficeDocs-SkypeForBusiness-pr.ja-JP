---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adaf9fe1c6d5d4cc0769810aece05bcb46681e79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Lync Server 2013 管理パックのインポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

System Center Operations Manager の機能を拡張するには、System Center Operations Manager が監視できるアイテム、およびそれらのアイテムを監視する方法と、アラートをトリガーする方法を決定するソフトウェアをインストールします。返さ. Lync Server 2013 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。

  - コンポーネントおよびユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話詳細記録 (CDR) または QoE (Quality of Experience) に記録します。databases. 重大な問題については、System Center Operations Manager を構成して、電子メール、インスタントメッセージ、またはショートメッセージサービス (SMS) のメッセージングを介して管理者に即座に通知できます。 SMS は、モバイル デバイス間でテキスト メッセージを送信するために使用されるテクノロジです。
    
    <div>
    

    > [!NOTE]  
    > Operations Manager 通知の構成の詳細については、TechNet ライブラリの「構成<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>の通知」を参照してください。

    
    </div>

  - アクティブな監視管理パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタントメッセージの交換、パブリックスイッチに配置された電話機への通話の作成などの主要な Lync Server コンポーネントを事前にテストします。電話網 (PSTN)。 これらのテストは、Lync Server 代理トランザクションコマンドレットを使用して行われます。 たとえば、**Test-CsIM** コマンドレットを使用すると、テスト ユーザーのペア間のインスタント メッセージング (IM) の会話をシミュレーションできます。 このシミュレーションされたメッセージの会話が失敗すると、通知が生成されます。

管理パックをインポートする必要があります。 管理パックをインポートしない場合、Operations Manager を使用して Lync Server イベントを監視したり、Lync Server 代理トランザクションを実行したりすることはできません。

コンポーネントおよびユーザー管理パックは、Lync Server 2013 の監視にのみ使用されます。 Lync Server 2013 と Lync Server 2010 の両方がインストールされている共存シナリオでは、lync server 2010 コンピューターで Lync Server 2010 管理パックを引き続き使用する必要があります。

<div>


> [!NOTE]  
> Lync server 2010 の管理パックには、Lync Server 2010 の監視管理パックと Lync Server の2010グループチャット監視管理パックが含まれています。



</div>

次のいずれかのツールを使用して、管理パックをインポートできます。

  - **System Center Operations manager**   この方法では、Operations manager を使用して Lync Server の監視を追加します。

  - **Operations manager シェル**   operations manager シェルを使用して、System Center Operations manager コンソールを使用して、管理パックのインポート時に発生した問題のトラブルシューティングを行うことができます。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1.  ファイル Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2013.Monitoring.ComponentAndUser.mp をダウンロードします。

2.  System Center Operations Manager で、[**管理**] をクリックします。

3.  [**管理**] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。

4.  [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5.  [**オンラインカタログ接続**] ダイアログボックスで、[**キャンセル**] をクリックして、Lync Server 管理パックの依存関係が存在するかどうかを、Operations Manager がオンラインにならないようにします。 System Center Operations Manager 2012 を使用している場合は、[**いいえ**] をクリックします。

6.  [**インポートする管理パックの選択**] ダイアログ ボックスで、ファイル **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** と **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** を探して選択し、[**開く**] をクリックします。ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。

7.  [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。

8.  [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。インポートとインストールの処理には数分かかることがあります。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用した管理パックのインポート

通常は、Operations Manager を使用して、管理パックをインポートする方が簡単です。ただし、エラーが発生してインポートが失敗した場合、コンソールは、適切なエラーレポートを常に提供するわけではありません。 これに対して、Operations Manager シェルは詳細情報を提供します。 Operations Manager を使用していて、管理パックのインポートで問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。 Operations Manager シェルには、インポートが失敗した理由を判断するのに役立つ情報が詳細に記載されています。

System Center Operations Manager 2007 R2 を使用している場合は、次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[ **System Center Operations manager 2007 R2**]、[ **operations manager Shell**] の順にクリックします。

2.  Operations Manager シェルで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Operations Manager シェルを閉じます。

System Center Operations Manager 2012 を使用している場合は、代わりに次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[ **Microsoft System Center 2012**]、[ **Operations manager**]、[ **operations manager Shell**] の順にクリックします。

2.  Operations Manager シェルで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

