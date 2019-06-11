---
title: 'Lync Server 2013: Lync PreCall ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync の PreCall のすべての診断ツール (Lync Server 2013)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-11-04_

Lync PreCall Diagnostics ツール (PCD) はクライアントベースのアプリケーションであり、ネットワークの現在の状態が、今後のエンタープライズ音声通話での音声品質にどのように影響するかを確認できます。

PCD は、ネットワークの最後のホップが脆弱である可能性が高い場合 (たとえば、公共の WiFi ネットワークまたはホームユーザーのノート pc など) に最も役立ちます。 PCD は、ネットワークのこの最終区間を走査する小さなパケットストリームを作成します。 このツールは、パケットストリームを分析して、この区間でのジッターと損失が通話品質にどのように影響するかを予測し、レポートを提供します。 PCD は、通話が行われているときでも、クライアントで継続的に実行できます。 パケットストリームは、帯域幅に大きな影響を与えません。

**PCD バージョン1.1 の最新のリリースには、次の機能強化が含まれています。**

  - 長いパスワードをサポートし、最大127文字まで使用できるようになりました。

  - 認証サインインの問題に関する追加診断

  - Lync ハイブリッド展開のサポートが向上

  - 資格情報ピッカーの更新

  - 安定性の向上

ご意見をお寄せいただき、ありがとうございます。 すべてのサポート質問または問題を[PCD のフィードバック](mailto:pcdfb@microsoft.com)エイリアスに<pcdfb@microsoft.com>送信してください。

このトピックには次のセクションがあります。

  - Lync PCD のバージョン

  - Lync PCD システム要件

  - Lync PCD の機能

  - Lync PCD を実行する

  - Lync PCD をアンインストールする

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD のバージョン

このトピックでは、無料でダウンロードできるツールの次のバージョンについて説明します。

  - Windows デスクトップアプリ ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD システム要件

<div>


> [!NOTE]  
> PCD をご利用になるには、ユニファイドコミュニケーション Web API (UCWA) をインストールして、Lync Server の展開でモバイルクライアントをサポートするように構成する必要があります。 UCWA は Lync Server と共にインストールされます。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows デスクトップアプリの要件

  - Windows 7 または Windows 8 オペレーティングシステムの任意のエディション

  - Microsoft .NET Framework 4.5 は、で入手できます。[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD の機能

Lync PCD には、次の機能が含まれています。

  - 既定ではオンデマンドで実行する (2 分バースト)

  - Always On (スナップビューで最大24時間) モードで実行する

  - テストの実行の履歴ビュー

  - サインインエラーの診断 (Windows 8 向け Lync PCD)

![LYNC PCD 機能のサインインの進行状況を示すスクリーンショット](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "LYNC PCD 機能のサインインの進行状況を示すスクリーンショット")

  - ネットワークメトリックのグラフィカル表示–ネットワーク MOS、パケット損失、および全画面表示とスナップビューでの着信のジッター。

**全画面表示**

![Precall 診断ツールのテスト結果グラフ](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Precall 診断ツールのテスト結果グラフ")

**スナップビュー**

![Precall のすべての診断ツールの使用率テスト結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Precall のすべての診断ツールの使用率テスト結果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Lync PCD を実行する

<div>

## <a name="running-windows-desktop-app"></a>Windows デスクトップアプリを実行している場合

1.  Windows 7 システムで PCD を開始するには、[**スタート**] メニューから [**すべての診断**を事前に実行] を選択します。
    
    Windows 8 システムで PCD を開始するには、スタート画面でアイコンを選ぶか、"すべての診断" を検索します。
    
    ![Precall 診断ツールアイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Precall 診断ツールアイコン")

2.  ツールが起動したら、資格情報を提供するための推奨される方法を選択し、[**すべての診断ツールのオプション**] ダイアログボックスでネットワークの動作モードを選択して、[ **OK]** を選択します。

3.  [**テストの開始**] ボタンを選択して診断の実行を開始します。
    
    [**ネットワーク資格情報を使用**する] オプションを選択した場合、テストは直ちに開始されます。
    
    [**資格情報を入力**する] オプションを選んだ場合は、[ **Windows セキュリティ**] ダイアログボックスが開きます。 資格情報を入力すると、テストが開始されます。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Lync PCD をアンインストールする

Lync PCD を削除するには、使用しているオペレーティングシステムの手順に従います。

  - Windows 7 システムでは、**コントロールパネル**を開き、[**プログラムと機能**] を選択して、[ **Lync 2013 precall Diagnostics**] をダブルクリックします。

  - Windows 8 システムでは、PCD タイルを右クリックして、スタート画面の下部にあるアプリバーから [**アンインストール**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

