---
title: 'Lync Server 2013: 更新機能をテストするためのデバイスを作成する'
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
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Lync Server 2013 で更新機能をテストするためのデバイスを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 (Lync Server 環境全体で)、または1つのサイト内でグローバルにデバイスをテストすることができます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは Lync Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。

<div>

## <a name="to-add-a-test-device"></a>テストデバイスを追加するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスのテスト**] をクリックします。

3.  [**新規作成**] をクリックし、[**グローバルテストデバイス**] または [**サイトテストデバイス**] をクリックします。

4.  次のいずれかを実行します。
    
      - [**グローバルテストデバイス**] をクリックした場合は、次の手順に進みます。
    
      - [**サイトテストデバイス**] をクリックした場合は、利用可能なサイトの一覧からサイトを選んで、[ **OK]** をクリックします。

5.  [**新しいテストデバイス**] で、デバイスの名前を [**デバイス名**] に入力します。

6.  [**識別子の種類**] で、[ **MAC アドレス**] または [**シリアル番号**] をクリックします。

7.  [**一意の識別子**] ボックスに、デバイスの MAC アドレスまたはシリアル番号を入力します。

8.  [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したテストデバイスの作成

テストデバイスは、Windows PowerShell と CsTestDevice コマンドレットを使用して作成できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

このコマンドレットを使用してテストデバイスを作成する場合は、次の2つの操作を行う必要があります。

  - IdentifierType として MACAddress またはシリアルを指定します。

  - デバイス Id を指定するときにスコープを含めます。 グローバルスコープで新しいデバイスを作成するには、次のような構文を使用します。
    
        -Identity "global/WindowsPhone"
    
    サイトスコープでテストデバイスを作成するには、次のような構文を使用します。
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>MAC アドレスを使ってテストデバイスを作成するには

  - このコマンドは、グローバルスコープでテストデバイスを作成し、MAC アドレスを IdentifierType として使用します。
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>シリアル番号を使用してテストデバイスを作成するには

  - このコマンドは、新しいテストデバイスを (Redmond サイトの) サイトのスコープで作成し、シリアル番号を IdentifierType として使用します。
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

詳細については、 [CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

