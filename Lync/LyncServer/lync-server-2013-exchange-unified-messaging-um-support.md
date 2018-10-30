---
title: 'Lync Server 2013: Exchange ユニファイド メッセージング (UM) のサポート'
TOCTitle: Exchange ユニファイド メッセージング (UM) のサポート
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48271264
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Exchange ユニファイド メッセージング (UM) のサポート

 

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 は、音声メッセージングと電子メール メッセージングを単一のメッセージング インフラストラクチャに結合するために、Exchange ユニファイド メッセージング (UM) との統合をサポートします。Exchange 2013 では、Exchange UM は、Exchange UM サービス (メールボックス サーバーにインストールされて実行される) と UM 通話ルーター (クライアント アクセス サーバーにインストールされて実行される) で構成されます。Lync Server 2013 のエンタープライズ VoIP 展開では、Exchange UM は、電話 (つまり Outlook Voice Access) またはコンピューターからアクセスできる単一ストアに音声メッセージングと電子メール メッセージングを結合します。Exchange UM と Lync Server 2013 は連動して、通話応答、Outlook Voice Access、および自動応答サービスをエンタープライズ VoIP のユーザーに提供します。

Exchange UM の社内展開との統合のサポートに加えて、Lync Server 2013 は、ホストされた Exchange UM との統合もサポートします。これにより、Microsoft Exchange Online などの Hosted Exchange サービス プロバイダーにユーザーの一部または全部を移行すると、音声メッセージングをユーザーに提供できるようになります。

Lync Server 2013 は、次のバージョンをサポートします。

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必須) または最新のサービス パック適用 (推奨)

  - Microsoft Exchange Server 2007 と Service Pack 1 (SP1) (必須) または最新のサービス パック (推奨)

Exchange UM は Lync Server 2013 または Lync Server 2013 データベースと共存することはできません。Exchange UM と Lync Server 2013 は別のフォレストにインストールできます。

> [!NOTE]
> PBX を展開済みのエンタープライズ VoIP 展開では、Exchange UM は必ずしも必要ではありません。なぜなら、PBX では引き続き、すべてのユーザーのボイス メールおよび関連サービスを提供できるからです。最終的に PBX の使用を停止する場合は (SIP トランキングを展開して公衆交換電話網 (PSTN) への接続性を確保する場合など)、これまで PBX ボイス メール システムを使用していたユーザーにボイス メールを提供するように Exchange UM を再構成する必要があります。


## このセクション中

  - [Lync Server 2013 の社内ユニファイド メッセージングのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 でのホスト型 Exchange UM 統合のサポート](lync-server-2013-support-for-hosted-exchange-um-integration.md)

