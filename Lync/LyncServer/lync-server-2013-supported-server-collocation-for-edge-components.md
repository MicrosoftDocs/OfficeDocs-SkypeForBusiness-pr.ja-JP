---
title: 'Lync Server 2013: エッジ コンポーネントのサポートされるサーバーの併置'
TOCTitle: エッジ コンポーネントのサポートされるサーバーの併置
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48271924
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での、エッジ コンポーネントのサポートされるサーバーの併置

 

_**トピックの最終更新日:** 2012-09-08_

アクセス エッジ サービス、Web 会議エッジ サービス、音声ビデオ エッジ サービス、および XMPP プロキシ サービスは、エッジ サーバーに併置されます。次のサーバーは、外部ユーザー アクセスに必要な機能を提供し、専用サーバーとして展開される必要があります。

  - エッジ サーバー

  - ディレクター (オプション)

  - リバース プロキシ


> [!IMPORTANT]
> リバース プロキシは Lync Server 2013 の提供専用である必要はありません。たとえば、Lync Server Web サービスを公開するサービスを提供しながら、公開された Web サイトを、Lync Server とはまったく関係のない他の Web サイトに提供できます。リバース プロキシ サーバーを、他のサービスをサポートするために境界ネットワーク上に既に展開している場合は、それを Lync Server 2013 にも使用できます。


