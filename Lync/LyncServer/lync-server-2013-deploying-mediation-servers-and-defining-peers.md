---
title: 'Lync Server 2013: 仲介サーバーの展開とピアの定義'
TOCTitle: 仲介サーバーの展開とピアの定義
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48273191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での仲介サーバーの展開とピアの定義

 

_**トピックの最終更新日:** 2012-09-21_

エンタープライズ VoIP のワークロード、ダイヤルイン会議、および高度な エンタープライズ VoIP アプリケーション (応答グループ アプリケーション、コール パーク アプリケーション、通話受付管理 (CAC) など) は、フロント エンド プールで使用できます。Lync Server 2013 では、仲介サーバーの機能が フロント エンド サーバーに組み込まれています。独立したスタンドアロンの 仲介サーバーは不要になりました。フロント エンド プールで、サポートされているゲートウェイ (公衆交換電話網 (PSTN) ゲートウェイまたは IP-PBX) と直接通信できるため、仲介サーバーによる仲介は必要ありません。

唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。エンタープライズ VoIP インフラストラクチャを SIP トランク プロバイダーに接続するには、独立した 仲介サーバーを展開する必要があります。

Lync Server (フロント エンド プールの 仲介サーバー コンポーネントまたはスタンドアロンの 仲介サーバー) とゲートウェイの間の接続は、*トランク* と呼ばれる論理的な関連付けとして定義されます。このセクションのトピックでは、トランクを定義する方法と、SIP トランクに接続する場合にスタンドアロンの仲介サーバーを展開する方法について説明します。

## このセクション中

  - [Lync Server 2013 のトポロジ ビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Lync Server 2013 での、トポロジ ビルダーを使用したゲートウェイの定義](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Lync Server 2013 仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Lync Server 2013 でのトポロジ ビルダーでの追加トランクの定義](lync-server-2013-define-additional-trunks-in-topology-builder.md)

## 関連項目

[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)

