---
title: 'Lync Server 2013: フロントエンド サーバー、インスタント メッセージング、およびプレゼンスに関する要件の定義'
TOCTitle: フロントエンド サーバー、インスタント メッセージング、およびプレゼンスに関する要件の定義
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48273495
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフロントエンド サーバー、インスタント メッセージング、およびプレゼンスに関する要件の定義

 

_**トピックの最終更新日:** 2013-10-07_

インスタント メッセージング (IM) とプレゼンスの計画における主なタスクは、ユーザーのために十分な数のフロントエンド サーバーを確保することです。

## 外部ユーザーとの通信の有効化

Lync Server への投資による収益性は、ユーザーが外部ユーザーと通信できるようにすることにより大幅に高めることができます。外部ユーザーには次のユーザーが含まれます。

  - **リモート ユーザー**   ファイアウォールの外側で自分のノート PC や他の Lync Server デバイスを使用して仕事をしている組織内のユーザー。

  - **フェデレーション ユーザー**   共同作業を行っている企業の、 Lync Server も実行しているユーザー。こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。

  - **パブリック ユーザー**   Windows Live ネットワーク インターネット サービス、Yahoo\!、および AOL によって提供される IM サービスなどのパブリック IM サービスのユーザー、および Google Talk などの XMPP (Extensible Messaging and Presence Protocol) を使用するプロバイダーおよびサーバーのユーザー。
    
    > [!NOTE]
    > ただし、Windows Live、AOL、Yahoo! とのパブリック IM 接続には、個別のライセンスが必要な場合があります。
    

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
    > <LI>
    > <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



これらのシナリオのいくつか、またはすべてを有効にするには、 Lync Server の展開と外部ユーザーの間でセキュリティで保護された通信を有効にできるようにエッジ サーバーを展開する必要があります。組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いのプレゼンスと通信を確認できるようになります。外部ユーザーとの通信の有効化の詳細については、「計画」のドキュメントの「[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

## IM コンテンツのアーカイブ

Lync Server には、組織で法令上の規制に従う必要がある場合に使用できる機能があります。アーカイブを使用すると、組織内のすべてのユーザーまたは指定する特定のユーザーの IM メッセージの内容をアーカイブすることができます。詳細については、「計画」のドキュメントの「[Lync Server 2013 のアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。

Microsoft Exchange Server 2013 も展開している場合は、 Exchange データのアーカイブと Lync Server データのアーカイブを統合して、1 つのツールを使用して両方の種類のアーカイブ データを検索することができます。詳細については、「[Microsoft Exchange Server 2013 アーカイブを使用するための Microsoft Lync Server 2013 の構成](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)」を参照してください。

