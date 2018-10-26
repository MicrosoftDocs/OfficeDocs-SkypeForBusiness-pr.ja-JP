---
title: 'Lync Server 2013: 外部ユーザー アクセスの新機能'
TOCTitle: 外部ユーザー アクセスの新機能
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48272941
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の外部ユーザー アクセスの新機能

 

_**トピックの最終更新日:** 2012-10-17_

Lync Server 2013 では、各種機能とユーザーの通信方法を拡張する新機能が導入されました。また、 Lync Server 2013 では既存のサービスも変更され、組織で使用できるサービスの統合性と拡張性が向上しました。ここでは、 Lync Server 2013  エッジ サーバー サービスの計画と展開に影響する可能性のある変更点の概要を説明します。

  - **IPv6 アドレスのサポート**     Lync Server 2013 は、すべての エッジ サーバー サービスで IPv6 アドレスをサポートしています。 Windows Server の構成でインターフェイスに IPv6 アドレスを指定している場合は、 トポロジ ビルダーの IP アドレス構成を通じて、 エッジ サーバーの構成で IPv6 アドレスを使用できます。
    

    > [!IMPORTANT]
    > Lync Server 2013 で IPv6 アドレスを使用するには、組織に展開されるルーターとファイアウォールが IPv6 をサポートしている必要があります。また、インターネット サービス プロバイダーも IPv6 をサポートしている必要があります。



  - **Extensible Messaging and Presence Protocol (XMPP)**     Lync Server 2013 には、完全統合型 XMPP プロキシ ( エッジ サーバーに展開) と、 フロント エンド サーバーに展開される XMPP ゲートウェイが導入されています。XMPP フェデレーションをオプションのコンポーネントとして導入できます。XMPP プロキシと XMPP ゲートウェイを追加および構成すると、 Microsoft Lync 2013 ユーザーは、XMPP ベースのパートナーからインスタント メッセージング (IM) およびプレゼンスの連絡先を追加できます。
    
    > [!NOTE]
    > 現在、 Lync Server 2013 の XMPP サービスは、 Lync クライアントと XMPP ベースの連絡先の間でのみインスタント メッセージングとプレゼンスを提供します。


  - **モバイル クライアント向けモビリティ サービス**     Lync Server 2010 の顧客更新で Lync Server 2013 のモビリティ サービスが導入されました。このモビリティ サービスにより、サポートされる Apple iOS、Android、Windows Phone、または Nokia の各モバイル デバイスを使用する携帯電話やタブレット上の Microsoft Lync Mobile クライアントは、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などの各種操作を実行できます。また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。
    
    > [!NOTE]
    > モビリティ サービスは、 フロント エンド サーバーに展開されるリバース プロキシと公開済みサービスを使用します。 エッジ サーバーに変更を加える必要はありません。


  - **ディレクターはオプションの役割**     Lync Server 2013 トポロジの ディレクター サーバーの役割に変更はありません。引き続き、Web サービスのホスト、受信ユーザー要求の事前認証、およびホーム プールへの外部ユーザーの送信を行います。 ディレクターが推奨される役割からオプションの役割に変更されることにより、 ディレクターの価値が下がるというわけではありません。むしろ、機能性を低下することなく、サーバー数やその他のハードウェア要件 ( ディレクターのロード バランサー機器など) を低減できます。 フロント エンド サーバーは、提供されているサービスに影響を与えることなく ディレクターと同じジョブを実行できるため、 ディレクターは必要な場合にのみオプションとして展開します。 フロント エンド サーバーが同じサービスを確実に提供するため、 ディレクターを安全に展開解除できます。

## 関連項目

#### 概念

[Lync Server 2013 での IPv6 の計画と構成](lync-server-2013-planning-for-and-configuring-ipv6.md)  

#### その他のリソース

[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 での XMPP (Extensible Messaging and Presence Protocol) フェデレーションの計画](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)

