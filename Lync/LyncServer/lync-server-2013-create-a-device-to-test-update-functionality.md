---
title: 'Lync Server 2013: 更新プログラムの機能をテストするデバイスを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 227ca68433cfcc41f966e220ffc826357b50d54b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Lync Server 2013 で更新プログラムの機能をテストするためのデバイスを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、(Lync Server 環境全体を通じて) グローバルに、または単一のサイト内で一括してテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは Lync Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。

<div>

## <a name="to-add-a-test-device"></a>テスト デバイスを追加するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**クライアント**] をクリックしてから、[**テスト デバイス**] をクリックします。

3.  [**新規**] をクリックし、[**グローバル テスト デバイス**] か [**サイト テスト デバイス**] のどちらかをクリックします。

4.  次のいずれかの操作を行います。
    
      - [**グローバル テスト デバイス**] をクリックした場合は、次の手順をスキップします。
    
      - [**サイト テスト デバイス**] をクリックした場合は、使用可能なサイトの一覧からサイトを選択して、[**OK**] をクリックします。

5.  [**新しいテスト デバイス**] の [**デバイス名**] にデバイスの名前を入力します。

6.  [**識別子の種類**] で、[**MAC アドレス**] または [**シリアル番号**] のどちらかをクリックします。

7.  [**一意識別子**] ボックスに、デバイスの MAC アドレスかシリアル番号を入力します。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してテストデバイスを作成する

テストデバイスは、Windows PowerShell と New-cstestdevice コマンドレットを使用して作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。

このコマンドレットを使用してテスト デバイスを作成するには、以下の 2 つを行う必要があります。

  - MACAddress または SerialNumber のいずれかを IdentifierType として指定します。

  - デバイス識別子を指定するときにスコープを含めます。グローバル スコープでデバイスを作成するには、次のような構文を使用します。
    
        -Identity "global/WindowsPhone"
    
    サイト スコープでテスト デバイスを作成するには、次のような構文を使用します。
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>MAC アドレスを使用してテストデバイスを作成するには

  - このコマンドはテスト デバイスを、グローバル スコープで、MAC アドレスを IdentifierType として使用して作成します。
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>シリアル番号を使用してテストデバイスを作成するには

  - このコマンドは新しいテスト デバイスを、サイトスコープ (Redmond サイト) で、シリアル番号を IdentifierType として使用して作成します。
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

詳細については、 [new-cstestdevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

