---
title: 'FAQ: Skype 接続用の Lync Server のプロビジョニング'
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
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>FAQ: Skype 接続用の Lync Server 2013 のプロビジョニング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2019-03-22_

2019年4月以降、pic.lync.com の web サイトから Skype フェデレーションを提供されているお客様の連絡先情報の収集と保持を停止します。 この変更は、pic.lync.com プロビジョニングシステムが Microsoft のプライバシーポリシーに準拠していることを確認するために行われています。 
 
この変更が有効になった後は、保留中のプロビジョニングの変更でメールの更新を提供することはできなくなります。 PIC プロビジョニングの変更は、通常、入力後の24-48 時間以内に完了します。 引き続き Skype フェデレーションの問題が発生した場合は、プロビジョニングリクエストの送信後に48時間がかかる場合は、Microsoft テクニカルサポートに協力して、さらに詳しく調査してください。

> [!IMPORTANT]
> この変更の一環として、以前に入力したすべての連絡先情報は、2019年4月のによってシステムから削除されます。


**Q: Microsoft Lync と Skype の間でサポートされている機能は何ですか?**

**A:** Skype を Microsoft ファミリの一部として使用することで、統合された通信シナリオを Skype を利用している無数のユーザーに拡張することができます。 この組み合わせによって、Lync のお客様は、Lync の豊富な機能と Skype の利用に基づいて、サプライヤー、顧客、パートナーとつながり、共同作業を行うことができます。

  - インスタントメッセージ (im)、音声通話、ビデオ通話-Lync と Skype ユーザ間でのチャットとビデオ通話、インスタントメッセージ (im)

  - プレゼンスの共有—フェデレーションされた連絡先間のプレゼンス情報の交換

  - 簡単な管理—組織のポリシーと標準に従ってフェデレーション通信を構成するための設定とコントロール

**Q: Lync の展開を Skype に接続するには、どうすればよいですか?**

**A:** 以下のいずれかをお持ちの場合は、Skype の接続が許諾されます。

  - Lync Server (2010 または 2013) に加えて、Lync Server Standard Client Access のライセンス (Cal "、2010、または 2013) と、Skype に接続する組織内のデバイスが含まれます。 

  - Lync Online (スタンドアロンライセンスとして、または Office 365 スイートの一部として)。ただし、このサービス (pic.lync.com) は、Lync Server およびハイブリッド Lync Server および Lync Online の展開のプロビジョニングのみを対象としています。Lync Online の PIC プロビジョニングは、Lync Online コントロールパネル (LOCP) で行われます。

**Q: Lync エンドユーザーが Skype の連絡先に接続するには何が必要ですか?**

**A:** ドメインをアクティブ化した後に、組織の Lync 管理者によって機能が有効になると、Lync ユーザーは Lync クライアント内の連絡先リストに Skype の連絡先を追加できます。

**Q: Skype エンドユーザが Lync の連絡先に接続するには、どうすればよいですか?**

**A:** Lync ユーザーに接続するすべての Skype ユーザーは、Skype Id に関連付けられた Microsoft アカウントを持っていて、Microsoft アカウントを使ってサインインする必要があります。これは、Skype クライアント内で有効にすることができます。

**Q: Windows Live とのフェデレーションはまだ利用できますか?**

**A:** 2012年10月から、Microsoft は、Windows Live Messenger (WLM) ユーザーが Skype に移行して、最終的に WLM の廃止に向けたサポートを開始しました。WLM が市場にある限り、Lync は WLM とのフェデレーションを引き続きサポートしますが、Windows Live ドメインのライセンス認証は追加されません。WLM ユーザの移動は、Skype 6.0 for Mac および Windows (2012 年10月25日リリース) によって有効にされています。これにより、Microsoft アカウント (つまり WLM と同じ資格情報) でサインインできます。 Skype にサインインするだけで、WLM の仲間リストが自動的に Skype に追加されます。また、ユーザは、固定電話や携帯電話への通話発信や、画面共有、グループビデオ通話、サポートなど、Skype の拡張された通信機能を利用できます。さまざまなデバイス。さらに、WLM ユーザのフェデレーションされた Lync の連絡先は、他の仲間リストを使用して Skype への切り替えを行った後、Skype と Lync の間の IM をすぐに利用できるようになります。 Lync のお客様は、このサービスの継続性を実現するために何もする必要はありません。

**Q: Yahoo\!または AOL とのフェデレーションはまだ利用できますか?**

**A:** 違います。 Yahoo とのフェデレーション\! また、AOL は Yahoo のサポートに応じて、\! および AOL。両方の Yahoo の場合\! AOL の場合、このサービスは2014年6月30日に終了しました。 

**Q: Lync を購入する前に Skype の接続を試用することはできますか?**

**A:** Skype の接続は、試用版では提供されていません。 試用の代わりに、適格なライセンスを持つ Lync のお客様には、サービスにサインアップしてテストすることをお勧めします。

**Q: プロビジョニングに必要な情報は何ですか?**

**A:** 認定されたライセンスの下でプロビジョニング要求を送信するには、次のものが必要です。

  - Microsoft 契約番号:
    
      - Microsoft ボリュームライセンスサポート: Microsoft ボリュームライセンス契約番号
    
      - Microsoft パートナーネットワーク: Headquarter パートナー ID
    
      - サービスプロバイダライセンス契約: 最初の登録番号
    
      - 高ボリュームサービス: 製品登録番号

  - アクセスエッジサービスの完全修飾ドメイン名 (Fqdn)。
    
      - 少なくとも1つのアクセスエッジサービスの FQDN が必要です。
    
      - アクセスエッジサービスを実行している複数のサーバーが組織で使用されている場合は、追加のアクセスエッジサービスごとに Fqdn を指定します。 重要: 以前にアクセスエッジサービスの FQDN を指定していて、それを変更する場合は、変更の準備が完了するまで数日間かかることがあり、サービスが中断される可能性があります。 サービスの中断を防ぐには、以前に指定したアクセスエッジサービスの FQDN を維持することをお勧めします。

  - セッション開始プロトコル (SIP) ドメイン。 これは、ユーザーが現在インスタントメッセージングに使用している SIP URI のドメインサフィックスです。 組織に複数の SIP ドメインがある場合は、インスタントメッセージング用に使用される各ドメインのドメインサフィックスを指定します。 たとえば、user1@contoso.com の場合、SIP ドメインの contoso.com を指定します。user1@example.fabrikam.com の場合は、SIP ドメインとして example.fabrikam.com を指定します。
    
    <div>
    

    > [!NOTE]
    > SIP ドメインのドメインサフィックスのみを指定します。 SIP ドメインのアクセスエッジサービスの FQDN など、どの Fqdn も指定しないでください。

    
    </div>

  - 連絡先情報。 指定した各 SIP ドメインの管理者の電子メールアドレスを指定します。

**Q: 切り離されるドメインシナリオで Lync を有効にするにはどうすればよいですか?**

**A:** Lync Online 2013 および Lync Server のオンプレミスの分割ドメインシナリオ (同じ SIP ドメインを使用して、オンラインとオンプレミスの両方のユーザーを含む) を使用している場合は、次の2つの手順を実行して、Lync-Skype の接続を有効にします。

1.  「PIC プロビジョニングガイド」で説明されているように、オンプレミスの Lync をセットアップします。

2.  ドメインが Microsoft によってプロビジョニングされたことを示す確認メッセージが表示されるまで待ちます。

3.  確認メッセージが表示されたら、Lync 管理センターを使用して、"外部通信" を有効にします。 詳細については、[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

この順序は重要です。Lync Online で通信を有効にする前に、オンプレミスの接続をセットアップする必要があります。 注文が取り消されると、オンプレミスで<https://pic.lync.com>入力された情報は移動しません。 このドメインとの外部通信用に Lync Online を既に設定している場合は、オンプレミス情報<https://pic.lync.com>を入力してから、lync online の外部通信を有効にする必要があります。

**Q: 複数のアクセスエッジサービスの Fqdn を Skype 接続用にプロビジョニングすることはできますか?**

**A:** 1つまたは複数のドメインに対して1つのアクセスエッジ FQDN のみをプロビジョニングできます。 個別のドメインがある場合は、要求ごとに最大10個のアクセスエッジ Fqdn をプロビジョニングできます。

**Q: プロビジョニングを要求する組織で見つかった Microsoft アカウントのメールアドレスの一覧を取得できますか。**

**A:** 違います。 これらのアドレスは、個人を特定できる情報と見なされ、共有されません。

**Q: windows Live でサポートされているもの以外のドメインを含む ID を持つ Windows Live Messenger の連絡先を追加するには、どうすればよいですか?**

**A:** Windows live Messenger を使って、windows live 以外のドメインを持つアカウントまたは ID を使用し\<ている場合は、[ユーザー名\>(\<ドメイン名\>) @msn .com] という\<形式のアドレスを入力\>します (このドメイン名は、ユーザーのメールアドレスのドメイン名です)。 たとえば、ted@contoso.com を追加する場合は、次の形式を使用します。 ted (コントソ) @msn。 Windows Live によって管理されるドメインの一覧については、の「Live Communications Server Service Pack 1 をインストールした後のパブリックインスタントメッセージングで発生する既知のhttp://support.microsoft.com/?kbid=897567問題」の「サポートされているドメイン」セクションを参照してください。

**Q: プロビジョニングプロセスにはどのくらいの時間がかかりますか?**

**A:** プロビジョニングには最長で30日間かかることがあります。

**Q: プロビジョニングが完了したことはどのように判断されますか?**

**A:** プロビジョニングが完了すると、Microsoft から電子メールで通知が送信されます。

**Q: 申請した構成や連絡先の詳細を更新するにはどうすればよいですか?**

**A:** プロビジョニングが完了した後で、プロビジョニングを要求するために使用したのと同じ web サイトで情報を更新することができます。 ライセンス契約番号を入力して、[サービスの更新] をクリックします。

</div>

<span> </span>

</div>

</div>

</div>

