---
title: 'Lync Server 2013: 組織内のデバイスのソフトウェア更新プログラムを表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1b1b4da0847dcc8242b6b514069d62a718c653f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Lync Server 2013 のデバイスのソフトウェア更新プログラムを表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 では、デバイス更新 Web サービスを使用して、組織のデバイスのソフトウェア更新プログラムを表示および管理します。 これらの更新プログラムは、から入手できます。 .cab (キャビネット) ファイルは[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)、Microsoft サポート web サイトから入手できます。 .Cab ファイルをダウンロードした後、**インポート-CSDeviceUpdate**コマンドレットを実行して、.cab ファイルからデバイス更新ルールをインポートします。 **インポート-csdeviceupdate**コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントの「[インポート-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 」を参照してください。

<div>


> [!TIP]  
> 新しい更新プログラムを組織に展開する前に、テストデバイスで正常に機能していることを確認してください。



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>UC デバイスのソフトウェア更新プログラムを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  の Microsoft サポート web サイトから[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)、.cab ファイルを Lync Server 2013 コンピューター上の場所 (たとえば、C:\\updates\\ucupdates .cab) にダウンロードします。

3.  次のいずれかのコマンドレットを実行\\し\\て、C: update ucupdates .cab ファイルからデバイス更新ルールをインポートします。
    
      - .Cab ファイルが、更新対象のサービス (サービス: Redmond-2) を実行しているコンピューターと同じコンピューターにある場合は、次のコマンドレットを実行します。
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - .Cab ファイルが、更新対象のサービス (サービス: Redmond-websvc-3) を実行しているコンピューターとは別のコンピューターにある場合は、次のコマンドレットを実行します。
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

5.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] をクリックします。

6.  [**デバイスの更新**] ページで、一覧から更新プログラムをクリックし、次のいずれかを実行します。
    
      - **保留中の更新をキャンセルします。** 選択した更新が組織のデバイスに展開されないようにするには、[**操作**] メニューをクリックし、[**保留中の更新の取り消し**] をクリックします。
    
      - **更新プログラムを承認します。** 選択した更新が組織のデバイスに展開されるようにするには、[**操作**] メニューをクリックし、[**承認**] をクリックします。
    
      - **更新プログラムを復元します。** 以前に承認した更新が組織のデバイスに展開されるようにするには、[**操作**] メニューをクリックし、[**復元**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

