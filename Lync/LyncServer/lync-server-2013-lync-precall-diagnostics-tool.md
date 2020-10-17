---
title: 'Lync Server 2013: Lync PreCall Diagnostics Tool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525154"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync PreCall Diagnostics Tool in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-11-04_

Lync PreCall Diagnostics Tool (PCD) はクライアントベースのアプリケーションで、これにより、ネットワークの現在の状態が今後のエンタープライズ Voip 通話の音声品質にどのように影響するかを確認できます。

PCD は、ネットワークの最後のホップが脆弱になる可能性がある状況 (たとえば、公共の WiFi ネットワークやホームユーザーのラップトップを使用している場合) に最も役立ちます。 PCD は、ネットワークの最終区間を通過する小さなパケットストリームを作成します。 次に、このツールは、パケットストリームを分析して、このレッグによるジッターと損失が通話品質にどのように影響するかを予測し、レポートを提供します。 通話が配置されている場合でも、PCD をクライアント上で継続的に実行することができます。 パケットストリームは、帯域幅に大きな影響を与えません。

**PCD バージョン1.1 の最新リリースには、次の機能拡張が含まれています。**

  - 長いパスワードのサポート。これで、最大127文字にすることができます。

  - 認証サインインの問題に関するその他の診断

  - Lync ハイブリッド展開のサポートの向上

  - 資格情報選択の更新

  - 安定性の向上

フィードバックは歓迎します。 すべてのサポートの質問または問題を [PCD フィードバック](mailto:pcdfb@microsoft.com) エイリアスに送信してください <pcdfb@microsoft.com> 。

このトピックには、以下のセクションが含まれます。

  - Lync PCD のバージョン

  - Lync PCD のシステム要件

  - Lync PCD の機能

  - Lync PCD を実行する

  - Lync PCD のアンインストール

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD のバージョン

このトピックでは、無料でダウンロードできる、次のバージョンのツールについて説明します。

  - Windows デスクトップアプリ ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD のシステム要件

<div>


> [!NOTE]  
> PCD では、Lync Server 展開のモバイルクライアントをサポートするように統合コミュニケーション Web API (UCWA) がインストールおよび構成されている必要があります。 UCWA は Lync Server と共にインストールされます。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows デスクトップアプリの要件

  - Windows 7 または Windows 8 オペレーティングシステムのすべてのエディション

  - Microsoft .NET Framework 4.5 で利用可能 [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD の機能

Lync PCD には、次の機能が含まれています。

  - 必要に応じて既定で実行する (2 分のバースト)

  - Always On で実行 (スナップビューで最大24時間) モード

  - テストの実行の履歴ビュー

  - サインインの失敗を診断する (Lync PCD for Windows 8 のみ)

![Lync PCD の機能サインインの進行状況を示すスクリーンショット](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD の機能サインインの進行状況を示すスクリーンショット")

  - ネットワーク指標のグラフィカルな表示–ネットワーク MOS、パケット損失、および全画面表示およびスナップビューでの着荷のジッター。

**全画面表示**

![PreCall 診断ツールのテスト結果グラフ](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診断ツールのテスト結果グラフ")

**スナップビュー**

![PreCall 診断ツールの使用テスト結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診断ツールの使用テスト結果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Lync PCD を実行する

<div>

## <a name="running-windows-desktop-app"></a>Windows デスクトップアプリを実行する

1.  Windows 7 システム上で PCD を開始するには、[**スタート**] メニューから [ **precall Diagnostics** ] を選択します。
    
    Windows 8 システム上で PCD を開始するには、スタート画面でアイコンを選択するか、または "PreCall Diagnostics" を検索します。
    
    ![PreCall 診断ツールアイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診断ツールアイコン")

2.  ツールが起動したら、資格情報を提供するために推奨される方法を選択し、[ **すべての診断ツールオプション** ] ダイアログボックスでネットワーク動作モードを選択して、[ **OK]** を選択します。

3.  [ **テストの開始** ] ボタンを選択して、診断の実行を開始します。
    
    [ **ネットワーク資格情報を使用** する] オプションを選択した場合、テストはすぐに開始されます。
    
    **[資格情報を入力**する] オプションを選択した場合は、[ **Windows セキュリティ**] ダイアログボックスが開きます。 資格情報を入力すると、テストが開始されます。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Lync PCD のアンインストール

Lync PCD を削除するには、オペレーティングシステムの手順に従います。

  - Windows 7 システムで、[ **コントロールパネル**] を開き、[ **プログラムと機能**] を選択して、[ **Lync 2013 precall Diagnostics**] をダブルクリックします。

  - Windows 8 システムで、PCD タイルを右クリックし、スタート画面の下部にあるアプリバーから [ **アンインストール** ] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

