---
title: Lync Server 2013 での SIP、XMPP フェデレーション、パブリック インスタント メッセージングの計画
TOCTitle: Lync Server 2013 での SIP、XMPP フェデレーション、パブリック インスタント メッセージングの計画
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48271812
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での SIP、XMPP フェデレーション、パブリック インスタント メッセージングの計画

 

_**トピックの最終更新日:** 2013-10-28_

内部ユーザーと外部ユーザーが、パートナーの組織またはサービスの連絡先にアクセスできるように、エッジ サーバーを構成できます。パートナーとの合意が既知であるため、フェデレーションにより、以下のいずれかまたはすべての機能が、パートナー フェデレーションにおける自組織内の連絡先または自組織へのパートナー フェデレーション内の連絡先に提供されます。

  - インスタント メッセージングおよびプレゼンス

  - グループ作業と会議 (Web 会議など)

  - 電話会議、ビデオ会議、またはその両方

通信は、Microsoft Lync Server 2013 と XMPP (Extensible Messaging and Presence Protocol) 連絡先との間のインスタント メッセージング (IM) およびプレゼンスのように、ピアツーピア専用で、自分とフェデレーション パートナーの連絡先のみがサポートされる場合があります。これとは別に、Lync Server、Lync Server 2010 と Lync Server 2013 のフェデレーションなどでは、複数の参加者を会話に招待できます。

## Lync Server と Office Communications Server のフェデレーション

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションは、ピアツーピアでマルチパーティの通信をサポートします。ピアツーピアの会話をマルチパーティの会話にエスカレートでき、臨時の会議を実行できます。会議 (Web 会議または音声ビデオ会議) をスケジュールし、組織内の連絡先およびフェデレーションしているパートナーの連絡先を含めることができます。

Microsoft Office Live Communications Server 2005 で初めて登場し、サポートされる唯一の種類のフェデレーションは、直接フェデレーションでした。直接フェデレーションでは、フェデレーション パートナーのセッション開始プロトコル (SIP) ドメインと、パートナーのエッジ サーバーの完全修飾ドメイン名 (FQDN) を知っている必要がありました。Live Communications Server 2005 SP1 ではフェデレーションの種類が追加されましたが、そのすべてで、エッジ サーバーを探すためにドメイン ネーム システム (DNS) SRV レコードがフェデレーション パートナーによって公開されている必要がありました。そのリリースで使用されていた用語は次のとおりです。

  - *オープン拡張フェデレーション*: あらゆる SIP ドメイン名を受け入れ、DNS SRV を使用してパートナー エッジ サーバーを探す

  - *拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーション パートナーとして構成し、DNS SRV を使用してパートナー エッジ サーバーを探す

  - *直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジ サーバーに対する FQDN を構成する

  - *サーバー許可リスト* : あらゆるドメインを受け入れ、DNS SRV を使用してホスティング プロバイダーまたはパブリック インスタント メッセージング (IM) 接続プロバイダーのエッジ サーバーを探す

Microsoft Office Communications Server 2007 では、各フェデレーションの種類で実際に行われることをより的確に表すように、フェデレーションの種類の名前が変更されました。

  - オープン拡張フェデレーションは、*検出済みのパートナー ドメイン*に変更

  - 拡張フェデレーションは、*許可されたパートナー ドメイン*に変更

  - 直接フェデレーションは、*許可されたパートナー サーバー*に変更

  - サーバー許可リストは、*ホスティング プロバイダー*および*パブリック IM プロバイダー*に変更

Microsoft Lync Server 2010 では、Microsoft Lync Online 2010 と Microsoft Office 365 に従ってホスティング プロバイダーの定義が狭められると共に、許可されたパートナー ドメインのフェデレーションの種類によって定義されるものと同じ許可リストに従うようになりました。

Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の間のフェデレーションを有効にすると、エッジ サーバーとリバース プロキシを使用して、ユーザーが定義するルールと許可されたパートナー ドメインが適用されます。計画の観点からは、他の Lync Server および Office Communications Server とのフェデレーションには以下が必要になります。

  - トポロジ ビルダーでフェデレーションを有効にします。詳しくは、「展開」のトピック「[Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)」をご覧ください。

  - フェデレーションされたドメインの検出に対する要件を決定します。
    
      - フェデレーションを手動で構成する場合、パートナーのエッジ サーバーの完全修飾ドメイン名 (FQDN) つまりオンライン ドメイン名が必要です。その名前を、Lync Server コントロール パネルの \[**フェデレーションと外部アクセス**\]、\[**SIP フェデレーション ドメイン**\] に入力します。FQDN によってドメインを許可または禁止するには、ポリシーを**新規作成**するか、既存のポリシーを**編集**します。
        

        > [!WARNING]
        > フェデレーション パートナーのエッジ サーバーを手動で構成すると、パートナーがエッジ サーバーの IP アドレスを変更したときにエラーが発生しやすくなります。

        
        > [!NOTE]  
        > [<strong>新規 SIP フェデレーション ドメイン</strong>] については、Microsoft Lync Online、Microsoft Office 365 の [<strong>ドメイン名 (または FQDN)</strong> ] を指定する必要があります。Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server については、[<strong>アクセス エッジ サービス (FQDN)</strong> ] も指定する必要があります。
    
      - 検出済みのパートナーのフェデレーションの場合、パートナーがこちらのエッジ サーバーを検出できますが、エッジ サーバーのポート 5061 およびホスト (A) レコードをポイントする SRV レコードを、こちらの外部 DNS に作成します (\_sipfederationtls.\_tcp.contoso.com)。
        

        > [!IMPORTANT]
        > Windows Phone または Apple iPhone、iPad、その他の Apple デバイス上で Microsoft Lync Mobile クライアントをサポートしており、プッシュ通知サービスまたは プッシュ通知サービスを使用している場合、Lync Mobile クライアントを使用する SIP ドメインごとに _sipfederationtls._tcp. <EM>&lt;SIP ドメイン&gt;</EM> の SRV レコードを計画する必要があります。Android と Nokia Symbian の Lync Mobile はプッシュ通知を使用しないため、この要件は適用されません。



  - フェデレーションされたドメインをサポートするように外部ユーザー アクセス ポリシーを構成します。

  - セッション開始プロトコル (SIP)、Web 会議、音声ビデオ用にファイアウォールのポートを開き、有効にしているフェデレーションまたは連絡先に対応します。詳しくは、「[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」をご覧ください。

Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーション用の証明書、ポート/プロトコル、DNS の要件を定義するときは、次の情報が役に立ちます。

証明書、ファイアウォール、ポート/プロトコルの要件、DNS の要件の計画は、Microsoft Lync Server 2013 エッジ サーバーを計画または展開してある場合は一般に簡単なプロセスです。フェデレーションは既存のエッジ サーバーを使用する追加機能なので、計画の要件は通常はエッジ サーバーの計画と展開によって満たされます。次の表を使用して要件が満たされていることを確認し、それに従ってポート/プロトコルおよび DNS を変更します。


> [!IMPORTANT]
> エッジ サーバーのプールがあり、Lync Server 2013 または Lync Server 2010 のパートナーとフェデレーションしている場合は、エッジ サーバーの内側または外側で DNS 負荷分散またはロード バランサー機器を使用できます。Office Communications Server 2007 または Office Communications Server 2007 R2 とフェデレーションしている場合は、ロード バランサー機器によってエッジ サーバーの場合のフェールオーバー サポートが提供されます。Office Communications Server 2007 および Office Communications Server 2007 R2 は、DNS 負荷分散には対応していません。パートナーのエッジ サーバーは、プール内で最初に応答したエッジ サーバーと通信を確立します。そのエッジ サーバーで障害が発生した場合、通信は自動的にはフェールオーバーしません。



証明書の要件は、通常、選択したエッジ サーバーまたはプールされたエッジ サーバーの計画に対する証明書の計画によって満たされます。

## パブリック インスタント メッセージング接続

パブリック インスタント メッセージング接続は、フェデレーションのクラスです。これを構成すると、Lync Server 2013 の内部ユーザーおよび外部ユーザーが、次のいずれかから連絡先を追加できます。

  - Messenger の連絡先

  - Yahoo\! の連絡先

  - America Online (AOL) の連絡先


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス (PIC USL) を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日 (正確な日付は未定ですが、2013 年 6 月以降です) まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約は更新されません。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続するための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Linc ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



このクラスのフェデレーションには、計画に関する次のような考慮が必要です。

  - Windows Live Messenger のユーザーは、Lync Server 2013 ユーザーと、インスタント メッセージングだけでなく、ピアツーピアの音声/ビデオ通信ができます。エッジ サーバーは、特定のポートおよびプロトコル要件を満たす必要があります。詳しくは、「[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」をご覧ください。

  - Yahoo インスタント メッセージングには、フェデレーションを提供している一般のエッジ サーバーの計画および展開で通常使用される要件以外に、固有の要件はありません。

  - America Online では、アクセス エッジ サービスに割り当てられている エッジ サーバー証明書にクライアント拡張キー使用法 (EKU) が含まれている必要があります。

## EMPP (xtensible Messaging and Presence Protocol) フェデレーション

以前のバージョンの Lync Server と Office Communications Server は、XMPP (Extensible Messaging and Presence Protocol) ゲートウェイを搭載し、このゲートウェイを独立したサーバーの役割として展開すると、XMPP 展開とのフェデレーションが行えました。Microsoft Lync Server 2013 では、XMPP 機能は機能として展開できます。XMPP 機能は 2 箇所にインストールされます。1 つは、エッジ サーバー上で実行される XMPP プロキシ、もう 1 つは、フロント エンド サーバー上で実行される XMPP ゲートウェイです。

XMPP の展開と構成については、「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」に記載されています。組織で XMPP のサポートを計画するには、ファイアウォールにポートとプロトコルの規則を定義し、証明書を構成して、DNS レコードを追加します。このセクションの以降のトピックに、展開の XMPP フェデレーションを適切に計画するのに必要な情報をまとめます。


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。




> [!IMPORTANT]
> XMPP フェデレーションは、存続可能ブランチ アプライアンスに所属するユーザーに対してはサポートされません。このことは、プレゼンス情報の表示と IM メッセージの交換の両方に当てはまります。



以下のトピックには、サポートされるフェデレーション シナリオの種類に応じた証明書、ファイアウォール ポート、DNS エントリの定義に関するガイダンスが記載されています。

  - [証明書の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [ポートの概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## 関連項目

#### タスク

[Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### 概念

[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  

#### その他のリソース

[Lync Server 2013 での組織のアクセス エッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

