---
title: Lync Server 2013 管理シェル
TOCTitle: Lync Server 2013 管理シェル
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48272354
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理シェル

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2010 では、Microsoft Office Communications Server 2007 R2 で使用可能であった機能と比べて、多くの新機能や強化された機能が導入されています。改善点の 1 つが実装方法です。たとえば、Lync Server コントロール パネルという新しいユーザー インターフェイスがあります。これは、多くのユーザーが Microsoft 管理コンソールで使い慣れたユーザー インターフェイスからの大幅な変更です。管理機能に関するその他の大きな改善点として、Windows PowerShell の追加があります。

Windows PowerShell を使用すると、Microsoft アプリケーションをコマンド ラインから管理できます。Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。Windows PowerShell は、2006 年後期に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理機能のコマンドライン インターフェイスとして組み込まれました。その時から進化を続け、ほとんどの Microsoft Server 製品 (最近では Microsoft Lync Server 2013) に組み込まれてきました。Lync Server 2010 には、約 550 個の製品固有のコマンドレットが導入されており、展開のあらゆる面の管理に使用できます。

次のセクションには、コマンドレットの一覧とその説明が含まれます。この情報は、コマンド ラインから直接入手することもできます。Lync Server 管理シェルのコマンド プロンプトに以下の内容を直接入力します。

    Get-Help <cmdlet name> -Full

たとえば、**New-CsVoicePolicy** コマンドレットに関するヘルプをコマンド プロンプトから取得するには、以下のように入力します。

    Get-Help New-CsVoicePolicy -Full

Lync Server 2013 の Windows PowerShell については、次の点に注意する必要があります。

  - Lync Server のコマンドレットを実行するには、Lync Server 管理シェルを開きます。
    

    > [!WARNING]
    > Lync Server 管理シェルではなく Windows PowerShell ウィンドウを開くと、既定では Lync Server コマンドレットを実行できません。Windows PowerShell 内から Lync Server のコマンドレットを実行するには、まず Windows PowerShell のコマンド プロンプトで以下の内容を入力します。<BR>Import-Module Lync



  - Lync Server 管理シェルは、すべての Lync Server Enterprise Edition のフロントエンド サーバーや Standard Edition サーバーに自動でインストールされます。

  - Windows PowerShell と Microsoft Lync Server 2013 のコマンドレットに関する新情報や更新された情報、サンプル スクリプト、および使用を開始して詳細を理解するためのヘルプについては、Lync Server Windows PowerShell ブログ ([http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x411)) を参照してください。

