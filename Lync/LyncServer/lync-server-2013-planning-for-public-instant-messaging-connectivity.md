---
title: パブリック インスタント メッセージング接続の計画
TOCTitle: パブリック インスタント メッセージング接続の計画
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48273896
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# パブリック インスタント メッセージング接続の計画

 

_**トピックの最終更新日:** 2017-03-09_

パブリック インスタント メッセージング接続は、フェデレーションのクラスです。これを構成すると、Lync Server 2013 の内部ユーザーおよび外部ユーザーが、次のいずれかから連絡先を追加できます。

  - Messenger の連絡先

  - Yahoo\! の連絡先

  - America Online (AOL) の連絡先


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス (PIC USL) を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! のサービス終了日は 2014 年 6 月と発表されています。詳しくは、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」をご覧ください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約は更新されません。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



このクラスのフェデレーションには、計画に関する次のような考慮が必要です。

  - Windows Live Messenger のユーザーは、Lync Server 2013 ユーザーと、インスタント メッセージングだけでなく、ピアツーピアの音声/ビデオ通信ができます。エッジ サーバーは、特定のポートおよびプロトコル要件を満たす必要があります。詳細については、「[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

  - Yahoo インスタント メッセージングには、フェデレーションを提供している一般のエッジ サーバーの計画および展開で通常使用される要件以外に、固有の要件はありません。

  - America Online では、アクセス エッジ サービスに割り当てられているエッジ サーバー証明書にクライアント拡張キー使用法 (EKU) が含まれている必要があります。

## このセクション中

  - [証明書の概要 - パブリック インスタント メッセージング接続](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [ポートの概要 - パブリック インスタント メッセージング接続](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS の概要 - パブリック インスタント メッセージング接続](https://technet.microsoft.com/ja-jp/library/jj618375\(v=ocs.15\))

