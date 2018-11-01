---
title: Lync PreCall 診断ツール
TOCTitle: Lync PreCall 診断ツール
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn451255(v=OCS.15)
ms:contentKeyID: 59602749
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync PreCall 診断ツール

 

_**トピックの最終更新日:** 2016-12-08_

Lync PreCall Diagnostics Tool (PCD) はクライアントベースのアプリケーションで、ネットワークの現在の状態が、予定されているエンタープライズ VoIP 通話の音声品質にどのように影響する可能性があるかを確認できます。

PCD が最も便利であるのは、ネットワークの最終ホップが最も弱い可能性が高い (たとえば、パブリック WiFi ネットワーク上のノート PC、またはホーム ユーザーが関与する) 状況です。PCD では、ネットワークのこの最終レグをスキャンする小さなパケット ストリームを作成します。続いて、このツールはパケット ストリームを分析して、このレグに沿ったジッターと損失が通話品質にどの程度影響するかを見積もり、レポートを提示します。通話が行われている最中でも、クライアント上で連続的に PCD を実行できます。パケット ストリームは、帯域幅に大きな影響を与えません。

**PCD の最新リリースであるバージョン 1.1 には、次の拡張機能が含まれています。**

  - 最大 127 文字の長いパスワードのサポート

  - 認証サインインの問題に対する追加の診断機能

  - Lync ハイブリッド展開のサポートの向上

  - Credential Picker の更新

  - 安定性の向上

Microsoft はフィードバックをお待ちしています。サポートに関するすべての質問や問題は、<pcdfb@microsoft.com> の [PCD Feedback](mailto:pcdfb@microsoft.com) エイリアスに送信してください。

このトピックには次のセクションがあります。

  - Lync PCD のバージョン

  - Lync PCD のシステム要件

  - Lync PCD の機能

  - Lync PCD の実行

  - Lync PCD のアンインストール

## Lync PCD のバージョン

このトピックでは、無料ダウンロードで入手できる、次のバージョンのツールについて説明します。

  - Windows デスクトップ アプリ ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

  - Windows 8 Modern アプリ ([http://go.microsoft.com/fwlink/?LinkId=322110](http://go.microsoft.com/fwlink/p/?linkid=322110))

> [!NOTE]
> Office 365 Lync のユーザーは、両方のバージョンの PCD を使用できます。


以前のバージョンの PCD を使用する場合は、以下を参照してください。

  - 32 ビット版の PCD は、Microsoft ダウンロード センター ([Office Communications Server 2007 R2, PreCallDiagnostic Resource Kit Tool (32 Bit)](http://go.microsoft.com/fwlink/p/?linkid=164769)) から無料でダウンロードできます。

  - 64 ビット版の PCD は、Microsoft ダウンロード センター ([Office Communications Server 2007 R2 Resource Kit Tools](http://go.microsoft.com/fwlink/p/?linkid=145159)) から無料でダウンロードできる Office Communications Server 2007 R2 Resource Kit Tools に含まれています。

## Lync PCD のシステム要件

> [!NOTE]
> PCD では、Unified Communications Web API (UCWA) がインストールされ、Lync Server 展開でモバイル クライアントをサポートするように構成されている必要があります。UCWA は Lync Server と共にインストールされます。


## Windows デスクトップ アプリの要件

  - すべてのエディションの Windows 7 または Windows 8 オペレーティング システム

  - Microsoft .NET Framework 4.5 ([http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790))

## Windows 8 Modern アプリの要件

  - すべてのエディションの Windows 8 オペレーティング システム

  - Microsoft .NET Framework 4.5 ([http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790))

## Lync PCD の機能

Lync PCD には次の機能が搭載されています。

  - 既定のオンデマンド設定での実行 (2 分のバースト)

  - 常時稼動状態での実行 (スナップ ビューで最長 24 時間) モード

  - テスト実行の履歴表示

  - サインイン エラーの診断 (Lync PCD for Windows 8 のみ)

![Lync PCD、サインイン進捗状況のスクリーンショット](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD、サインイン進捗状況のスクリーンショット")

  - ネットワーク指標のグラフィカル表示 – 全画面表示とスナップ ビューでのネットワーク MOS、パケット損失、および到着間ジッター。

**全画面表示**

![PreCall 診断ツールのテスト結果のグラフ](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診断ツールのテスト結果のグラフ")

**スナップ ビュー**

![PreCall 診断ツール、使用状況テストの結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診断ツール、使用状況テストの結果")

## Lync PCD の実行

## Windows デスクトップ アプリの実行

1.  Windows 7 システムで PCD を起動するには、\[**スタート**\] メニューから \[**PreCall Diagnostics**\] を選びます。
    
    Windows 8 システムで PCD を起動するには、スタート画面のアイコンを選ぶか、"PreCall Diagnostics" を検索します。
    
    ![PreCall 診断ツール アイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診断ツール アイコン")

2.  ツールが起動したら、資格情報を提供する優先方法を選び、\[**PreCall Diagnostics Tool Options**\] ダイアログ ボックスでネットワークの動作モードを選び、\[**OK**\] を選びます。

3.  \[**Start Test**\] ボタンを選んで、診断の実行を開始します。
    
    \[**Use network credentials**\] オプションを選んだ場合、テストはすぐに始まります。
    
    \[**Let me enter my credentials**\] オプションを選んだ場合、**Windows のセキュリティ**に関するダイアログ ボックスが表示されます。資格情報を入力した後、テストが始まります。

## Windows 8 Modern アプリの実行


1.  PCD を起動するには、スタート画面のアイコンを選ぶか、"PreCall Diagnostics" を検索します。
    
    ![PreCall 診断ツール アイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診断ツール アイコン")

2.  ツールが起動したら、Lync の資格情報を入力し、\[**OK**\] を選びます。
    
    ![Lync PreCall 診断ツール サインイン](images/Dn451255.88039914-4c68-48f6-a9fa-58cb4e3f3488(OCS.15).jpg "Lync PreCall 診断ツール サインイン")

3.  \[**Start test**\] ボタンを選んで、診断の実行を開始します。

## Lync PCD のアンインストール

Lync PCD を削除するには、オペレーティング システムに応じた手順を実行します。

  - Windows 7 システムでは、**コントロール パネル** を開き、\[**プログラムと機能**\] を選んで、\[**Lync 2013 PreCall Diagnostics**\] をダブルクリックします。

  - Windows 8 システムでは、PCD のタイルを右クリックし、スタート画面の下部にあるアプリ バーから \[**アンインストール**\] をクリックします。

