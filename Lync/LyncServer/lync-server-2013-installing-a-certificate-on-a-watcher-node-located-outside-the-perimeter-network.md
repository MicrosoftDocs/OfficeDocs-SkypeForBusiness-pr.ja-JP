---
title: 境界ネットワーク外にある監視ノードの証明書のインストール
TOCTitle: 境界ネットワーク外にある監視ノードの証明書のインストール
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49887023
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 境界ネットワーク外にある監視ノードの証明書のインストール

 

_**トピックの最終更新日:** 2016-12-08_

境界ネットワークで (Lync Server エッジ サーバーなど)、エンタープライズの外部で (外部代理トランザクション監視ノードなど)、または Active Directory ドメイン サービス の信頼境界を越えて、System Center Operations Manager エージェントが実行する場合は、System Center Operations Manager ゲートウェイ サーバーの構成が必要になる場合があります。このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。詳細については、System Center Operations Manager TechNet ライブラリの「Operations Manager 2007 におけるゲートウェイ サーバーの管理」([http://go.microsoft.com/fwlink/?linkid=268703\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268703%26clcid=0x411)) を参照してください。

これらの場所のいずれかにエージェントを展開する場合は、監視ノードが System Center Operations Manager に警告を送信できるようにする証明書を要求して構成する必要もあります。このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。これらのユーティリティの詳細とダウンロードについては、ブログ記事「証明書作成ウィザードによる簡略化された非ドメインに参加しているエージェントに対する証明書取得の方法」([http://go.microsoft.com/fwlink/?linkid=267421\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=267421%26clcid=0x411)) を参照してください。

