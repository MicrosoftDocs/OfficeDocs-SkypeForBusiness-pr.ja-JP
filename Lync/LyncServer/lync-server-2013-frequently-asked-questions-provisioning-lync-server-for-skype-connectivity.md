---
title: 'よく寄せられる質問: Skype 接続用の Lync Server のプロビジョニング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3679999bc12f606fe338652e8bef22e455cec9ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>よく寄せられる質問: Lync Server 2013 を Skype 接続用にプロビジョニングする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2019-03-22_

2019年4月から、pic.lync.com web サイトを介して Skype フェデレーションを準備されているお客様の連絡先情報の収集と保存を停止します。 この変更は、pic.lync.com プロビジョニングシステムが Microsoft プライバシーポリシーに準拠していることを確認するために行われます。 
 
この変更が有効になると、保留中のプロビジョニング変更に対する電子メール更新を提供することができなくなります。 PIC プロビジョニングの変更は、通常、入力されてから24-48 時間以内に完了します。 準備要求の提出後、Skype フェデレーションの問題が依然として48時間発生している場合は、さらに詳しく調査するために Microsoft テクニカルサポートにご協力ください。

> [!IMPORTANT]
> この変更の一環として、以前に入力したすべての連絡先情報は、2019年4月の終了後にシステムから削除されます。


**Q: Microsoft Lync と Skype との間でサポートされている機能は何ですか。**

**A:** Skype を Microsoft ファミリの一部に追加することで、Skype を使用している無数のユーザーに統合コミュニケーションのシナリオを拡張するための新しい可能性が広がりました。 この組み合わせにより、Lync のお客様は、Lync の豊富な機能と Skype の利用に依存して、パートナー、顧客、パートナーとの接続と共同作業を行うことができます。

  - インスタントメッセージと音声およびビデオ通話: Lync および Skype ユーザー間のフェデレーション音声およびビデオ通話、およびインスタントメッセージング

  - プレゼンスの共有—フェデレーションの連絡先間でのプレゼンス情報の交換

  - シンプルな管理—組織のポリシーと基準に従ってフェデレーション通信を構成するための設定と制御

**Q: Lync 展開を Skype に接続するにはどうすればよいですか。**

**A:** 次のいずれかの場合、Skype 接続がライセンスされています。

  - Lync Server (2010 または 2013) と、Skype に接続する組織内のユーザーまたはデバイスの Lync Server Standard クライアントアクセスライセンス ("CALs"; 2010 または 2013)。 

  - Lync Online (スタンドアロンライセンスまたは Office 365 スイートの一部)。ただし、このサービス (pic.lync.com) は、Lync Server とハイブリッド Lync Server および Lync Online の展開のプロビジョニングにのみ使用されます。Lync online PIC プロビジョニングは、Lync Online コントロールパネル (LOCP) で行われます。

**Q: Lync エンドユーザーが Skype の連絡先に接続するにはどうすればよいですか。**

**A:** ドメインがアクティブ化され、組織の Lync 管理者によって機能が有効になると、Lync ユーザーは Lync クライアント内の連絡先リストに Skype 連絡先を追加することができます。

**Q: Skype エンドユーザーが Lync の連絡先に接続するにはどうすればよいですか?**

**A:** Lync ユーザーに接続するすべての Skype ユーザーには、Skype Id に関連付けられた Microsoft アカウントがあり、Microsoft アカウントを使用してサインインする必要があります。これは、Skype クライアントで有効にすることができます。

**Q: Windows Live とのフェデレーションはまだ利用可能ですか?**

**A:** 2012年10月から、Microsoft は Windows Live Messenger (WLM) ユーザーを Skype に移行する手助けを開始しました。これで、最終的に WLM を撤去することになります。Lync は、WLM が市場にある限り、WLM とのフェデレーションを引き続きサポートしますが、Windows Live ドメインのライセンス認証を追加することは許可されません。WLM ユーザーの移動は、Skype 6.0 for Mac および Windows (2012 年10月25日リリース) によって有効になります。これにより、Microsoft アカウント (つまり、WLM と同じ資格情報) でサインインできます。 Skype にサインインするだけで、WLM の友人リストは Skype に自動的に追加され、ユーザーは、固定電話と mobiles の呼び出し、画面共有、グループビデオ通話、およびワイドのサポートなど、Skype の拡張された通信機能を活用できます。さまざまなデバイス。さらに、WLM ユーザーのフェデレーションされた Lync 連絡先は、他の仲間リストを使用して Skype への移行を実行し、これらの連絡先の Skype と Lync 間の IM はすぐに使用できるようになります。 Lync のお客様は、このサービスの継続性を有効にするために何もする必要はありません。

**Q: Yahoo\!または AOL とのフェデレーションは引き続き利用できますか?**

**A:** 違います。 Yahoo とのフェデレーション\! および AOL は、Yahoo からのサポートを受けています。\! および AOL。両方の Yahoo\! AOL の場合、サービスは2014年6月30日に終了します。 

**Q: Lync を購入する前に Skype の接続を試用することはできますか?**

**A:** Skype 接続は、試用版では提供されていません。 試用版の代わりに、ライセンスを受けている Lync のお客様は、単にサービスにサインアップすることをお勧めします。

**Q: プロビジョニングに必要な情報について教えてください。**

**A:** 認定されたライセンスの下でプロビジョニング要求を送信するには、次のものが必要です。

  - Microsoft 契約番号:
    
      - Microsoft ボリュームライセンスサポート: Microsoft ボリュームライセンス契約番号
    
      - Microsoft パートナーネットワーク: Headquarter パートナー ID
    
      - サービスプロバイダ使用許諾契約書: 最初の登録番号
    
      - 高ボリュームサービス: 製品登録番号

  - アクセスエッジサービスの完全修飾ドメイン名 (Fqdn)。
    
      - 少なくとも1つのアクセスエッジサービスの FQDN が必要です。
    
      - アクセスエッジサービスを実行している複数のサーバーが組織にある場合は、追加のアクセスエッジサービスごとに Fqdn を指定します。 重要: 以前にアクセスエッジサービスの FQDN を指定していて、それを変更する場合は、変更の準備が完了するまでに数日かかる場合があり、サービスが中断する可能性があります。 サービスが中断しないようにするには、アクセスエッジサービスの以前に指定した FQDN を維持することをお勧めします。

  - セッション開始プロトコル (SIP) ドメイン。 これは、ユーザーがインスタントメッセージングに現在使用している SIP URI のドメインサフィックスです。 組織に複数の SIP ドメインがある場合は、インスタントメッセージングに使用される各ドメインのドメインサフィックスを指定します。 たとえば、user1@contoso.com では、SIP ドメインの contoso.com を指定します。user1@example.fabrikam.com では、SIP ドメインとして example.fabrikam.com を指定します。
    
    <div>
    

    > [!NOTE]
    > SIP ドメインのドメインサフィックスのみを指定します。 SIP ドメインでは、アクセスエッジサービスの FQDN を含む任意の Fqdn を指定しないでください。

    
    </div>

  - 連絡先情報。 指定した各 SIP ドメインの管理者の電子メールアドレスを指定します。

**Q: 分割ドメインシナリオで Lync-Skype 接続を有効にするにはどうすればよいですか?**

**A:** Lync Online 2013 および Lync Server のオンプレミスの分割ドメインシナリオがあり、(同じ SIP ドメインを使用してオンラインとオンプレミスの両方でユーザーがいる場合)、次の2つの手順を実行して Lync-Skype 接続を有効にします。

1.  「PIC プロビジョニングガイド」で説明されているように、オンプレミスの Lync-Skype 接続をセットアップします。

2.  ドメインが Microsoft によってプロビジョニングされたことを確認するメッセージが表示されるまで待機します。

3.  確認が表示されたら、Lync 管理センターを使用して "外部通信" を有効にします。 詳細については、[https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

この順序は重要です。Lync Online で通信を有効にする前に、オンプレミス接続をセットアップする必要があります。 順序を逆にした場合、でオンプレミスで<https://pic.lync.com>入力された情報は通過しません。 このドメインとの外部通信に既に Lync Online をセットアップしている場合は、これをオフにし、24時間待機してから、もう一度開始します。最初<https://pic.lync.com>に、オンプレミス情報を入力してから、lync Online の外部通信を有効にしてください。

**Q: Skype 接続用に複数のアクセスエッジサービス Fqdn をプロビジョニングできますか。**

**A:** 1つ以上のドメインに対して1つのアクセスエッジ FQDN のみをプロビジョニングできます。 個別のドメインがある場合、複数のアクセスエッジの Fqdn をプロビジョニングすることができ、要求ごとに最大10個。

**Q: プロビジョニングを要求している組織に対して見つかった Microsoft アカウントの電子メールアドレスの一覧を取得できますか。**

**A:** 違います。 これらのアドレスは個人を特定できる情報と見なされ、共有されません。

**Q: Windows Live でサポートされているドメイン以外のドメインを含む ID を持つ Windows Live Messenger の連絡先を追加するにはどうすればよいですか?**

**A:** Windows live 以外のドメインを持つアカウントまたは ID を使用して windows live Messenger ユーザーを追加する場合は、アドレスを次の形式\<で入力\>し\<ます。\>ユーザー名 (ドメイン名) \<@msn .com\> 。ドメイン名は、ユーザーの電子メールアドレスのドメイン名です。 たとえば、ted@contoso.com を追加する必要がある場合は、次の形式を使用します。 ted () @msn .com。 Windows Live によって管理されるドメインの一覧については、「Live Communications Server Service Pack 1 をインストールした後のパブリックインスタントメッセージングに関する既知の問題」 https://support.microsoft.com/?kbid=897567の「サポートされるドメイン」セクションを参照してください。

**Q: プロビジョニングプロセスにはどのくらいの時間がかかりますか?**

**A:** プロビジョニングには最大30日間かかることがあります。

**Q: プロビジョニングが完了すると、どのように通知されますか。**

**A:** プロビジョニングが完了すると、Microsoft は電子メール通知を送信します。

**Q: 提出した構成または連絡先の詳細を更新するにはどうすればよいですか?**

**A:** 準備の完了後に、プロビジョニングの要求に使用したのと同じ web サイトで情報を更新することができます。 契約番号を入力し、[サービスの更新] をクリックします。

</div>

<span> </span>

</div>

</div>

</div>

