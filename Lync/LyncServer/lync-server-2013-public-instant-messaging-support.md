---
title: 'Lync Server 2013: パブリック インスタント メッセージングのサポート'
TOCTitle: パブリック インスタント メッセージングのサポート
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48271467
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのパブリック インスタント メッセージングのサポート

 

_**トピックの最終更新日:** 2013-10-07_

Lync Server 2013 では、ライセンスされたパブリック インスタント メッセージング (IM) 接続プロバイダーの使用がサポートされています。さらに、XMPP (eXtensible Messaging and Presence Protocol) を使用した特別な種類のフェデレーションの実装もサポートされており、Lync Server で Lync 2013 クライアントを使用して、構成済み XMPP ドメイン パートナーにアクセスできます。

## パブリック IM 接続プロバイダーのサポート

現在サポートされているパブリック インスタント メッセージング接続パートナーは次のとおりです。

  - America Online

  - Windows Live

  - Yahoo\!

Windows Live ユーザーとの通信では、Lync Server 2013 はピアツーピア IM および音声通話とビデオ通話をサポートしています。AOL および Yahoo\! との通信では、Lync Server 2013 はピアツーピア IM をサポートしています。別途ライセンスが必要になることがあります。


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



## XMPP フェデレーションのサポート

XMPP フェデレーションにより、Lync ユーザーは GTalk などのパブリック プロバイダーを使用する構成済み XMPP ドメイン ユーザーと通信することができます。これらのユーザーとの通信では、次の機能を使用できます。

  - ピアツーピア IM とプレゼンス

  - XMPP フェデレーションからの連絡先を Lync クライアントに作成

