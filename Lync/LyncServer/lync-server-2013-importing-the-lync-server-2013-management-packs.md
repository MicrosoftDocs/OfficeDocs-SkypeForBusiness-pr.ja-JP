---
title: Lync Server 2013 管理パックのインポート
TOCTitle: Lync Server 2013 管理パックのインポート
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48272703
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理パックのインポート

 

_**トピックの最終更新日:** 2016-12-08_

管理パックをインストールすることで、System Center Operations Manager の機能を拡張できます。管理パックは、System Center Operations Manager が監視できる項目、それらの項目を監視する方法、および通知をトリガーして報告する方法が示されているソフトウェアです。Lync Server 2013 には 2 つの System Center Operations Manager 管理パックが含まれ、以下の機能が提供されます。

  - Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベント ログに記録されたり、パフォーマンス カウンターによって登録されたり、通話詳細記録 (CDR) データベースや Quality of Experience (QoE) データベースに記録されたりした Lync Server の問題を追跡します。重大な問題については、電子メール、インスタント メッセージ、または Short Message Service (SMS) メッセージングで管理者にすぐに通信するように、System Center Operations Manager を構成できます。SMS は、モバイル デバイス間でテキスト メッセージを送信するために使用されるテクノロジです。
    
    > [!NOTE]
    > Operations Manager 通知の構成の詳細については、TechNet ライブラリの「通知の構成」(<a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x411</a>) を参照してください。


  - Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタント メッセージの交換、公衆交換電話網 (PSTN) に存在する電話の呼び出しなど、Lync Server の重要なコンポーネントに対する予防的なテストを行います。これらのテストは、Lync Server の代理トランザクション コマンドレットを使用して実施されます。たとえば、**Test-CsIM** コマンドレットを使用すると、テスト ユーザーのペア間のインスタント メッセージング (IM) の会話をシミュレーションできます。このシミュレーションされたメッセージの会話が失敗すると、通知が生成されます。

管理パックをインポートする必要があります。管理パックをインポートしないと、Operations Manager を使用して Lync Server のイベントを監視したり、Lync Server の代理トランザクションを実行したりすることができません。

Component and User Management Pack は、Lync Server 2013 の監視にのみ使用されます。Lync Server 2013 と Lync Server 2010 の両方がインストールされている併置シナリオの場合、Lync Server 2010 のコンピューターには引き続き Lync Server 2010 管理パックを使用する必要があります。

> [!NOTE]
> Lync Server 2010 用の管理パックには、Lync Server 2010 Monitoring Management Pack と Lync Server 2010 Group Chat Monitoring Management Pack が含まれます。


次のいずれかのツールを使用して、管理パックをインポートできます。

  - **System Center Operations Manager**   この方法では、Operations Manager を使用して Lync Server の監視を追加します。

  - **Operations Manager シェル**   Operations Manager シェルを使用して、管理パックを直接インポートしたり、System Center Operations Manager コンソールで管理パックをインポートするときに発生した問題をトラブルシューティングしたりできます。

## System Center Operations Manager を使用した管理パックのインポート

1.  ファイル Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2013.Monitoring.ComponentAndUser.mp をダウンロードします。

2.  System Center Operations Manager で \[**管理**\] をクリックします。

3.  \[**管理**\] ウィンドウで、\[**管理パック**\] を右クリックして \[**管理パックのインポート**\] をクリックします。

4.  \[**管理パックの選択**\] ダイアログ ボックスで、\[**追加**\] をクリックし、\[**ディスクから追加する**\] をクリックします。

5.  \[**オンライン カタログ接続**\] ダイアログ ボックスで \[**キャンセル**\] をクリックして、Lync Server 管理パックに依存関係が存在するかどうかを確認するために Operations Manager がオンラインにならないようにします。System Center Operations Manager 2012 を使用している場合は、\[**いいえ**\] をクリックします。

6.  \[**インポートする管理パックの選択**\] ダイアログ ボックスで、ファイル **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** と **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** を探して選択し、\[**開く**\] をクリックします。ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。

7.  \[**管理パックの選択**\] ダイアログ ボックスで、\[**インストール**\] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。

8.  \[**管理パックの選択**\] ダイアログ ボックスで、\[**閉じる**\] をクリックします。インポートとインストールの処理には数分かかることがあります。

## Operations Manager シェルを使用した管理パックのインポート

一般には、管理パックをインポートするには Operations Manager を使用する方が簡単です。ただし、エラーが発生してインポートが失敗する場合、コンソールでは適切にエラーが報告されないことがあります。これに対し、Operations Manager シェルでは詳細な情報が提供されます。Operations Manager を使用していて、管理パックのインポートに問題がある場合は、Operations Manager シェルを使用してパックをインポートしてください。Operations Manager シェルではインポートが失敗した理由の特定に役立つ可能性のある詳細な情報が提供されます。

System Center Operations Manager 2007 R2 を使用している場合は、次の手順を実行します。

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**System Center Operations Manager 2007 R2**\] の順にクリックし、\[**Operations Manager シェル**\] をクリックします。

2.  Operations Manager シェルのコマンド プロンプトで次のコマンドを入力して、Enter キーを押します。パスには、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーの実際のパスを使用します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Operations Manager シェルを閉じます。

System Center Operations Manager 2012 を使用している場合は、以下の手順を使用します。

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft System Center 2012**\]、\[**Operations Manager**\] の順にクリックし、\[**Operations Manager シェル**\] をクリックします。

2.  Operations Manager シェルのコマンド プロンプトで次のコマンドを入力して、Enter キーを押します。パスには、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーの実際のパスを使用します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

