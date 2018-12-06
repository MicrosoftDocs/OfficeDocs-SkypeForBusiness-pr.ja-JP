---
title: テスト更新機能へのデバイスの作成
TOCTitle: テスト更新機能へのデバイスの作成
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48273664
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# テスト更新機能へのデバイスの作成

 

_**トピックの最終更新日:** 2013-02-23_

\[**テスト デバイス**\] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。デバイスをグローバルに (Lync Server 環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。デバイスを追加すると、そのデバイスが Lync Server コントロール パネルの \[**テスト デバイス**\] ページの一覧に表示されます。

## テスト デバイスを追加するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**クライアント**\] をクリックしてから、\[**テスト デバイス**\] をクリックします。

3.  \[**新規**\] をクリックし、\[**グローバル テスト デバイス**\] か \[**サイト テスト デバイス**\] のどちらかをクリックします。

4.  次のいずれかの操作を行います。
    
      - \[**グローバル テスト デバイス**\] をクリックした場合は、次の手順をスキップします。
    
      - \[**サイト テスト デバイス**\] をクリックした場合は、使用可能なサイトの一覧からサイトを選択して、\[**OK**\] をクリックします。

5.  \[**新しいテスト デバイス**\] の \[**デバイス名**\] にデバイスの名前を入力します。

6.  \[**識別子の種類**\] で、\[**MAC アドレス**\] または \[**シリアル番号**\] のどちらかをクリックします。

7.  \[**一意識別子**\] ボックスに、デバイスの MAC アドレスかシリアル番号を入力します。

8.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットを使用してテスト デバイスを作成する

テスト デバイスは Windows PowerShell および New-CsTestDevice コマンドレットを使用して作成できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

このコマンドレットを使用してテスト デバイスを作成するには、以下の 2 つを行う必要があります。

  - MACAddress または SerialNumber のいずれかを IdentifierType として指定します。

  - デバイス識別子を指定するときにスコープを含めます。グローバル スコープでデバイスを作成するには、次のような構文を使用します。
    
        -Identity "global/WindowsPhone"
    
    サイト スコープでテスト デバイスを作成するには、次のような構文を使用します。
    
        -Identity "site:Redmond/WindowsPhone"

## MAC アドレスを使用してテスト デバイスを作成するには

  - このコマンドはテスト デバイスを、グローバル スコープで、MAC アドレスを IdentifierType として使用して作成します。
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

## シリアル番号を使用して、テスト デバイスを作成するには

  - このコマンドは新しいテスト デバイスを、サイトスコープ (Redmond サイト) で、シリアル番号を IdentifierType として使用して作成します。
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

詳細については、[New-CsTestDevice](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTestDevice) コマンドレットに関するヘルプ トピックを参照してください。

