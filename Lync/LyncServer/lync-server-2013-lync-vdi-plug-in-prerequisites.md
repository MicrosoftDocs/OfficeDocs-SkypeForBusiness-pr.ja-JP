---
title: 'Lync Server 2013: Lync VDI プラグインの前提条件'
description: 'Lync Server 2013: Lync VDI プラグインの前提条件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566543"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013 での lync VDI プラグインの前提条件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-07_

仮想デスクトップインフラストラクチャ (VDI) 環境では、仮想マシンとユーザーのローカルコンピューターが、このセクションで説明する要件を満たしている必要があります。

<div>


> [!NOTE]  
> 仮想化環境のインストール方法および展開方法の詳細については、仮想化ソリューション プロバイダーに問い合わせてください。Hyper-V およびリモート デスクトップ サービスに基づいた仮想化環境の展開については、Microsoft TechNet ライブラリの次の記事を参照してください。 
> <UL>
> <LI>
> <P>Hyper-v <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Windows Server &nbsp; 2008 R2 のリモートデスクトップ &nbsp; サービス <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

データ センターのコンピューターで実行されている仮想マシンに対する要件は次のとおりです。

  - 仮想マシンは、最新のサービスパックを使用して Windows 10、windows 8.1、Windows 8、Windows 7、または Windows Server 2008 R2 で構成する必要があります。

ユーザーとユーザーのローカルコンピューターの要件は次のとおりです。

  - ユーザーは、Lync Server 2013 に所属している必要があります。

  - ローカルコンピューターでは、Windows Embedded Standard 7 SP1、windows 7 SP1、windows 8、Windows 8.1 が埋め込まれているか、または Windows 8.1 (埋め込まれていない) を実行している必要があります。

  - リモートデスクトップサービスを使用している場合、Lync VDI プラグインのビット数 (つまり、アプリケーションが32ビットであるか、または64ビットであるか) は、ローカルコンピューターのオペレーティングシステムのビット数と一致している必要があります。 ローカル コンピューターと仮想マシンのオペレーティング システムのビット数が一致する必要はありません。 別の仮想化ソリューションまたは仮想化プラットフォームを使用している場合は、ビット数の要件については、仮想化ソリューション プロバイダーのガイダンスを参照してください。

  - ローカル コンピューターは、最新バージョンのリモート デスクトップ クライアントを実行している必要があります。 マイクロソフトからリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 最新のリモートデスクトップサービスの更新については、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 。

  - ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート録音が無効となるように構成する必要があります。 Windows でこれらの設定をリモートデスクトップ接続用に構成するには、次のセクション「リモートデスクトップ接続の設定を構成するには」を参照してください。

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成するには

Windows で Lync VDI プラグインのリモートデスクトップ接続を準備するには、次の手順を実行します。

1.  ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップします。 ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンのリモートデスクトップサービスクライアントをインストールし [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) ます。

2.  [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。

3.  [**オプション**] をクリックします。

4.  [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
      - [**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。
    
      - [**リモート オーディオ録音**] の下の [**録音しない**] を選択します。
    
      - [**OK**] をクリックします。

5.  [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。

6.  [**全般**] タブをクリックします。[**コンピューター**] で仮想マシンの名前を入力し、[**接続**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

