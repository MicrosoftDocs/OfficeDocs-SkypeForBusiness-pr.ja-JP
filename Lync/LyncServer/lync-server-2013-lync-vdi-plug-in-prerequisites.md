---
title: 'Lync Server 2013: Lync VDI プラグインの前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013 の Lync VDI プラグインの前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-03-07_

仮想デスクトップインフラストラクチャ (VDI) 環境では、仮想マシンとユーザーのローカルコンピューターがこのセクションで示されている要件を満たしている必要があります。

<div>


> [!NOTE]  
> 仮想化された環境をインストールして展開する方法の詳細については、仮想化ソリューションプロバイダーを参照してください。 Hyper-v とリモートデスクトップサービスに基づいて仮想環境を展開する方法については、Microsoft TechNet ライブラリの次の記事を参照してください。 
> <UL>
> <LI>
> <P>Hyper-v<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Windows Server&nbsp;2008&nbsp;R2 のリモートデスクトップサービス (at)<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

データセンターコンピューターで実行されている仮想マシンの要件を次に示します。

  - 仮想マシンは、最新の service pack を使用して、Windows 10、Windows 8.1、Windows 8、windows 7、または Windows Server 2008 R2 で構成する必要があります。

ユーザーとユーザーのローカルコンピューターの要件を次に示します。

  - ユーザーは、Lync Server 2013 上に置かれている必要があります。

  - ローカルコンピューターでは、SP1、Windows 7 SP1、Windows 8、windows 8.1 Embedded、または Windows 8.1 (埋め込み以外) で Windows Embedded 標準7を実行している必要があります。

  - リモートデスクトップサービスを使用している場合は、Lync VDI プラグインビット (つまり、32ビットと64ビットのどちらであるか) がローカルコンピューターのオペレーティングシステムのビットと一致している必要があります。 ローカルコンピューター上のオペレーティングシステムと仮想マシン上のオペレーティングシステムのビットが一致している必要はありません。 別の仮想化ソリューションまたはプラットフォームを使用している場合は、「ビット要件について仮想化ソリューションプロバイダーからのガイダンス」を参照してください。

  - ローカルコンピューターで、最新バージョンのリモートデスクトップクライアントが実行されている必要があります。 Microsoft からリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 最新のリモートデスクトップサービスの更新につい[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)ては、を参照してください。

  - ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート レコーディングが無効となるように構成する必要があります。 Windows でリモートデスクトップ接続のこれらの設定を構成するには、次のセクション「リモートデスクトップ接続設定を構成する」を参照してください。

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>リモートデスクトップ接続設定を構成するには

Windows で Lync VDI プラグインのリモートデスクトップ接続を準備するには、次の手順を実行します。

1.  ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップしてください。 ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンのリモートデスクトップサービスクライアントをインストール[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)します。

2.  [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。

3.  [**オプション**] をクリックします。

4.  [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
      - [**リモート オーディオ再生**] で [**このコンピューターで再生**] を選択します。
    
      - [**リモート オーディオ録音**] で [**録音しない**] を選択します。
    
      - [**OK**] をクリックします。

5.  [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] で [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。

6.  [**全般**] タブをクリックします。[**コンピューター**] で、仮想マシンの名前を入力し、[**接続**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

