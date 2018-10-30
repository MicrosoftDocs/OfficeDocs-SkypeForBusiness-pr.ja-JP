---
title: 'Lync Server 2013: ホスト型 Exchange UM 統合のサポート'
TOCTitle: ホスト型 Exchange UM 統合のサポート
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48273559
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのホスト型 Exchange UM 統合のサポート

 

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 ExUM ルーティング アプリケーションは、社内環境で Exchange ユニファイド メッセージング (UM) との統合をサポートします。この環境では、次の図のように、 Lync Server 2013 と Exchange UM の両方が、社内でローカルに (サービス プロバイダーにホストされる Exchange UM と共に) インストールされます。

![社内の Lync Server Exchange UM 展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "社内の Lync Server Exchange UM 展開")

次のモードがサポートされています。

  - **社内モード**Lync Server 2013 および Exchange UM は社内のローカル サーバーに展開されます。

  - **横断設置型モード**Lync Server 2013 は社内のローカル サーバーに展開され、 Exchange UM は Microsoft Exchange Online データ センターなどのオンライン サービス プロバイダーの設備にホストされます。

  - **混合型モード**Lync Server 2013 展開に社内の Microsoft Exchange Server を実行するローカル サーバーに属するユーザー メールボックスも、Hosted Exchange サービス データ センターに属するメールボックスも存在します。
    
    > [!NOTE]
    > 混合型モードは、評価のため段階的にホスト型 Exchange UM にユーザーを移行する間の暫定的なソリューションとして、または、他のユーザーを移行した後に、一部のユーザーの Exchange UM サービスを内部設置型とする場合の恒久的なソリューションとして使用できます。


Lync Server 2013 とホスト型 Exchange UM を統合するには、 *共有 SIP アドレス スペース* ( *分割ドメイン* ) を構成する必要があります。この構成では、 Lync Server 2013 とサードパーティ両方のホスト型 Exchange UM サービス プロバイダーが同じ SIP ドメイン アドレス スペースにアクセスできます。詳細については、「計画」のドキュメントの「[Lync Server 2013 の Hosted Exchange UM 統合のアーキテクチャ](lync-server-2013-hosted-exchange-um-integration-architecture.md)」を参照してください。

