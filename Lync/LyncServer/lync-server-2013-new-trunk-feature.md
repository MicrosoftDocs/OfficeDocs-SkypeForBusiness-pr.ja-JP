---
title: 'Lync Server 2013: 新しいトランク機能'
TOCTitle: 新しいトランク機能
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49887068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の新しいトランク機能

 

_**トピックの最終更新日:** 2012-09-21_

Microsoft Lync Server 2013 では、仲介サーバーとゲートウェイの間で複数のトランクを定義できます。Microsoft Lync Server 2010 では、仲介サーバー と PSTN ゲートウェイの間で使用できるトランクは 1 つだけでした。これにより、必要に応じて追加のトランクを定義できるようになりました。トランクとは、仲介サーバーの FQDN およびリッスン ポートと PSTN ゲートウェイの FQDN およびリッスン ポートの間の論理的な関連付けです。この新機能により、復元 (複数の仲介サーバーを使用して同じ PSTN ゲートウェイに通話をルーティングできます)、PBX 相互運用 (異なるポリシーが関連付けられた複数のトランクを IP-PBX と 仲介サーバーの間で使用できます)、および SIP トランク構成 (同じキャリア FQDN によって参照されるキャリアへの SIP トランクを複数のサイトの 仲介サーバーに割り当てることができます) のためのトランクの定義が簡単になります。

## 関連項目

#### 概念

[Lync Server 2013 の新しいエンタープライズ VoIP 機能](lync-server-2013-new-enterprise-voice-features.md)

