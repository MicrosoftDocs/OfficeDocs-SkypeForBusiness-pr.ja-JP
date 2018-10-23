---
title: ハイブリッド接続を計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ビジネス オンラインまたはチームの業務サーバーの Skype と Skype との間のハイブリッドの接続を実装するための考慮事項を計画しています。
ms.openlocfilehash: 34df2639ed57376549b2a8bde2e4b0e071d08957
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696234"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Skype ビジネス サーバーと Office 365 のハイブリッド接続を計画します。

## <a name="overview"></a>概要

ビジネス オンラインまたはチームの業務サーバーの Skype と Skype との間のハイブリッドの接続を計画する方法については、このトピックを参照してください。 多くの Skype for Business ハイブリッド ソリューションを展開する上で、ハイブリッド接続の設定は最初に行う手順となります。

ハイブリッド ソリューションは、マイクロソフトのクラウドで提供されているオンラインのサービスも活用しながらいくつかの設置型のコントロールを保持するを有効にします。 ハイブリッド接続の設定、および、オンラインで使用できるクラウド サービスとオンプレミス ユーザーのさまざまな、ユーザーをスケジュールし、ビジネス ニーズに基づいて、クラウドに移動するを選択できます。

たとえば、設置 PSTN への接続を維持しながらマイクロソフトの電話システムをクラウドでの呼制御を取得することができます。 クラウドのボイスメールやデータの電話コネクタなど、他のクラウド サービスを活用することもできます。

設置型で、Active Directory は - 作成されたユーザーとビジネスのサーバー環境を既存のオンプレミス Skype と Skype との間のハイブリッドの接続を構成する必要があります、インフラストラクチャおよびシステムの要件について説明します。ビジネスをオンラインまたはチームです。

このトピックを読んでいるし、ハイブリッドの接続を構成する準備ができている後、は、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。 構成に関するトピックでは、オンライン ビジネスの設置型展開と Skype との間のハイブリッドの接続をセットアップするためのステップ バイ ステップのガイダンスを提供します。

(Lync Server 2013、ハイブリッドの Lync Server 2010 展開を構成する方法の詳細については、 [Lync Server 2013 ハイブリッド](https://go.microsoft.com/fwlink/p/?LinkId=617360)を参照してください)。

## <a name="split-domain-functionality"></a>ドメインの機能を分割します。
<a name="BKMK_Overview"> </a>

 ハイブリッド接続がビジネスをオンラインまたはチームの Skype ビジネス サーバー用の設置型展開と Skype の設定、いくつかのユーザー ホーム設置型を持つことができ、一部のユーザーがオンライン ホームします。

この種類の構成は、分割ドメイン」--つまり、contoso.com などのドメインのユーザーは、複数を使用して Skype の社内のビジネス サーバーと Skype のオンライン ビジネスやチームの次の図に示すように分割されるとも呼ばれます。

![SfB ハイブリッド接続 - 分割ドメイン](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

分割ドメイン環境の場合。

- 施設内に置かれているユーザーは、ビジネスのサーバーの設置型の Skype と対話します。 クラウド ボイスメールなどのオンライン サービスへのアクセスにもあります。

- オンラインが置かれているユーザーは、企業やチームのオンライン サービスの Skype と対話可能性があります。

- 両方の環境からのユーザーでは、インスタント メッセージング、電話会議や VoIP 電話をかけたりに参加しているを使用して、相互に共同作業でき、ためにすることができます。

- Azure Active Directory 接続は、Office 365 で、設置ディレクトリを同期する使用されます。

オンプレミスの Active Directory は優先されるため、次のことを実行してオンプレミスおよびオンラインのユーザーが相互に検出できるようにする必要があります。

- すべてのユーザーは、最初に、オンプレミスの Active Directory 内に作成し、Azure AD に同期する必要があります。

- クラウドへの移行は、ユーザーには、ビジネス計画の 2 またはチームのライセンスのいずれか、Skype が必要です。

- Skype 会議をブロードキャストやクラウドのボイスメールなどの他のオンライン機能を利用する場合は、ユーザーは、Office 365 の適切なライセンスを割り当てる必要があります。

- ライセンスが割り当てられた Sype for Business Online ユーザーについては、Skype for Business またはオンプレミスの Enterprise Voice を有効にする必要があります。 詳細については、[社内設置型のエンタープライズ VoIP のユーザーを有効にする](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)を参照してください。 ハイブリッド音声の要件の詳細については、「[Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)」を参照してください。


## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
<a name="BKMK_Infrastructure"> </a>

オンプレミス環境と Office 365 の通信サービスとの間のハイブリッドの接続を実装するには、次のインフラストラクチャ要件を満たす必要があります。

- 1 つ設置 Skype のビジネス サーバーまたはサポートされているトポロジに展開されている Lync Server の展開です。 このトピックでは、[トポロジの要件](plan-hybrid-connectivity.md#BKMK_Topology)を参照してください。

- 有効にし、ビジネス オンラインの Skype での Microsoft Office 365 テナントです。

    > [!NOTE]
    > オンプレミス展開があるハイブリッド構成には、1 つのテナントしか使用できません。

- Business Server 管理ツールの Skype です。 (Lync Server 2013 または Lync Server 2010 を使用する場合することができます、Lync Server 2013 管理ツールを使用します。 について詳細については、「 [Lync Server 2013 ハイブリッド](https://go.microsoft.com/fwlink/p/?LinkId=617360))

- オンプレミスのディレクトリを Office 365と同期させる Azure Active Directory Connect。 詳細についてを参照してください[Azure AD 接続: アカウントとアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

    ユーザーがオンプレミスで使用するものと同じログイン資格情報を使用できるように Office 365 でのシングル サインオンをサポートする場合、Azure Active Directory (AAD) Connect のパスワード同期機能を使用できます。 また、Office 365 でのシングル サインオンに Active Directory フェデレーション サービス (AD FS) を使用することもできます。 

ハイブリッド接続を構成するには、オンプレミスとオンライン環境では、間のフェデレーションを設定し、共有セッション開始プロトコル (SIP) アドレス スペースのオンライン ビジネスのテナントは、Skype を構成する必要も。 ハイブリッド接続を構成する手順の詳細については、[ハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。

ハイブリッド接続を構成した後は、オンライン ビジネスやチームの Skype にユーザーを移動できます。 詳細については、[ビジネス オンラインの Skype への設置型からユーザーを移動](move-users-from-on-premises-to-skype-for-business-online.md)し、[設置をチームからユーザーを移動する](move-users-from-on-premises-to-teams.md)を参照してください。

## <a name="multi-forest-support"></a>マルチ フォレストのサポート
<a name="BKMK_MultiForest"> </a>

ユーザーは、次の要件が満たされれば、別のフォレストで Skype for Business の機能にアクセスできます。

- ユーザーが、Skype for Business をホストするフォレストに適切に同期されている。ハイブリッド構成において、これはユーザーが無効化されたユーザー オブジェクトとして同期される必要があることを意味します。

- Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。

ハイブリッドの複数のフォレスト シナリオの詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](configure-a-multi-forest-environment-for-hybrid.md)を参照してください。

## <a name="administrator-credentials"></a>管理者の資格情報
<a name="BKMK_Credentials"> </a>

管理者の資格情報を提供するメッセージが表示されたらを使用してユーザー名とパスワード管理者アカウントに、Office 365 テナントのです。 フェデレーション、ディレクトリ同期、シングル サインオン、および移動ユーザーが Skype のオンライン ビジネスの Azure Active Directory を構成するときにも、これらの資格情報を使用します。

## <a name="skype-for-business-online-powershell"></a>Skype for Business Online PowerShell
<a name="BKMK_PowerShell"> </a>

管理者には、オンライン ビジネス、オンライン ビジネスのユーザー アカウントに対して、Skype の Skype を管理するために Windows PowerShell を使用する機能があるようになりました。 これを行うには、まずダウンロードして、Microsoft ダウンロード センターからオンライン コネクタ モジュールをビジネス用の Skype をインストールします。 ダウンロード、インストール、およびコネクタ モジュールのオンライン ビジネス、およびビジネスのオンラインの Skype を管理するために Windows PowerShell を使用しての詳細については、Skype を使用する方法については、 [Windows PowerShell には、コンピューターの設定](https://technet.microsoft.com/library/dn362831.aspx)を参照してください。

## <a name="skype-for-business-client-support"></a>Skype for Business のクライアント サポート
<a name="BKMK_ClientSupport"> </a>

クライアントでサポートされる機能には違いがあります。また、オンプレミス環境とオンライン環境で使用できる機能にも違いがあります。 次のクライアントは、ハイブリッド展開で、Skype で、ビジネスをオンラインでサポートされます。

- Skype for Business

- Lync 2013

- Lync 2010

- Lync Windows ストア アプリ

- Lync Web App

- Lync Mobile

- Lync for Mac 2011

- Lync ルームのシステムとビジネス ルーム システムの Skype

- Lync Basic 2013

- Microsoft Surface Hub

ホーム ユーザー、組織内を決定する前に、クライアントのサポート、さまざまな Skype のビジネスのサーバーの構成を決定する[ビジネス用の Skype のデスクトップ クライアントの機能の比較](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)を表示します。 以下の項目もご覧ください。

- [クライアントおよびデバイスの計画](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Skype for Business のモバイル クライアント機能の比較](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>トポロジ要件
<a name="BKMK_Topology"> </a>

Skype でオンライン ビジネスのハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかである必要があります。

- ビジネス サーバー 2015 の Skype を実行しているすべてのサーバーとサーバー 2015 のビジネス展開するための Skype です。

- Lync Server 2013 を実行しているすべてのサーバーに Lync Server 2013 展開します。

    ハイブリッド音声接続をフェデレーションするエッジに指定されているエッジ サーバーがビジネス 2015; の Skype をする必要があります。エッジには、ビジネス サーバーのバックエンドは、Skype も必要です。 ユーザーのいないプールを持つことができます。

- Lync Server 2010 を最新の累積的な更新プログラムを実行しているすべてのサーバーに Lync Server 2010 展開します。

  - エッジ サーバーのフェデレーションおよびエッジ サーバーのフェデレーションからの次ホップ サーバーする必要があります実行している Lync Server 2010 を最新の累積的な更新プログラム。

  - ビジネス サーバー 2015 または Lync Server 2013 の管理ツールの Skype が少なくとも 1 つのサーバーまたは管理ワークステーション上にインストールしなければなりません。

- 混合 Lync Server 2013、Skype ビジネス サーバー 2015 の Skype を実行するには、少なくとも 1 つのサイトで次のサーバーの役割を持つサーバー 2015 のビジネス展開に。

  - 少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー 

  - SIP フェデレーションに関連づけられたディレクター プール (もしあれば)

  - SIP フェデレーションに関連づけられたエッジ プール (もしあれば)

- 混合 Lync Server 2010、Skype ビジネス サーバー 2015 の Skype を実行するには、少なくとも 1 つのサイトで次のサーバーの役割を持つサーバー 2015 のビジネス展開に。

  - 少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー 

  - SIP フェデレーションに関連づけられたディレクター プール (もしあれば)

  - サイトの SIP フェデレーションに関連づけられたエッジ プール

- Lync Server 2013 を実行している少なくとも 1 つのサイトで次のサーバーの役割を組み合わせた Lync Server 2010 および Lync Server 2013 展開します。

  - サイトの少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー

  - SIP フェデレーションに関連づけられたディレクター プール (もしサイトにあれば)

  - サイトの SIP フェデレーションに関連づけられたエッジ プール

## <a name="federation-allowedblocked-lists-requirements"></a>フェデレーション許可/禁止の一覧の要件
<a name="BKMK_Federation"> </a>

許可されたドメイン] ボックスの一覧には、構成されているパートナー エッジ完全修飾ドメイン名 (FQDN) を持つドメインが含まれています。 これは、許可されたパートナー サーバーと呼ばまたは、直接フェデレーション パートナー。 開いているフェデレーションと終了と呼ばれるパートナーの検出および許可されたパートナー ドメイン] ボックスの一覧、それぞれ、設置型展開でフェデレーションの違いを理解する必要があります。

ハイブリッド展開を正しく構成するには、次の必要条件を満たす必要があります。

- オンプレミス展開と Office 365 テナントでドメイン マッチングの構成を同一にする必要があります。オンプレミス展開でパートナーの検出が有効になっている場合、オンライン テナントではオープン フェデレーションを有効にする必要があります。パートナーの検出が無効になっている場合、オンライン テナントではクローズド フェデレーションを構成する必要があります。

- オンプレミス展開における禁止ドメインの一覧はオンライン テナントの禁止ドメインの一覧と正確に一致する必要があります。

- オンプレミス展開における許可ドメインの一覧はオンライン テナントの許可ドメインの一覧と正確に一致する必要があります。

- オンラインのテナントは、コントロール パネルのオンライン ビジネスを Skype を使用して構成されているため、外部との連絡には、フェデレーションを有効にする必要があります。

## <a name="dns-settings"></a>DNS の設定
<a name="BKMK_DNS"> </a>

ハイブリッド展開用の DNS レコードを作成するには、外部の DNS レコードをビジネスのすべての Skype はオンプレミス インフラストラクチャを指し示します。 必要な DNS レコードの詳細については、 [Skype ビジネス サーバー用の DNS の要件](../../sfbserver/plan-your-deployment/network-requirements/dns.md)を参照してください。

また、設置型展開で、次の表に記載されている DNS 解決が正しく動作することを確認する必要があります。

|DNS レコード  <br/> |解決方法  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls._tcp の DNS SRV レコードです。\<sipdomain.com\>サポートされているすべての SIP ドメインがアクセス エッジの外部 IP(s) に解決するため  <br/> |エッジ サーバー  <br/> |ハイブリッド展開でフェデレーション通信を有効にする。オンプレミスとオンラインで分割される SIP ドメイン用のフェデレーション トラフィックのルートをエッジ サーバーで認識している必要があります。  <br/> ユーザー名のドメインと SRV レコードの間で一致する厳密な DNS 名を使用する必要があります。  <br/> |
|エッジ Web 会議サービス FQDN の DNS A レコード、たとえば、webcon.contoso.com は Web 会議のエッジ外部 IP に解決される  <br/> |ユーザーのコンピューターが社内ネットワークに接続されています。  <br/> |オンライン ユーザーを有効にして、オンプレミスのホストされた会議でのコンテンツを提供または表示する。コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモがあります。  <br/> |

所属する組織での DNS の構成方法によっては、内部 DNS 解決をこれらのレコードに適用するために、対応する SIP ドメインに対して組織内でホストする DNS ゾーンにこれらのレコードを追加する必要があります。

## <a name="firewall-considerations"></a>ファイアウォールの考慮事項
<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services のデータ ・ センターの場所、によって、ワイルドカード ドメイン名に基づいて接続を許可するのには、ネットワークのファイアウォール デバイスを構成する必要がありますも (からのすべてのトラフィックは、 \*. outlook.com)。 組織のファイアウォールはワイルドカードの名前の構成をサポートしていない場合は、許可したい IP アドレスの範囲、指定されたポートを手動で確認する必要があります。

詳細については、「[Office 365 URL および IP アドレス範囲](https://go.microsoft.com/fwlink/p/?LinkId=252942)」を参照してください。

## <a name="port-and-protocol-requirements"></a>ポートとプロトコルの要件
<a name="BKMK_Ports"> </a>

内部通信に必要なポートのほかに、次のポートも構成して、ハイブリッド接続を有効にする必要があります。


|**プロトコル**|**TCP または UDP**|**発信元 IP アドレス**|**送信先 IP アドレス**|**発信元ポート**|**宛先ポート**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |アクセス エッジ  <br/> |Office 365  <br/> |任意  <br/> |5061  <br/> |信号  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |アクセス エッジ  <br/> |任意  <br/> |5061  <br/> |信号  <br/> |
|STUN  <br/> |TCP  <br/> |音声ビデオ エッジ  <br/> |Office 365  <br/> |50000 - 59999  <br/> |443、50000 - 59999  <br/> |音声、ビデオ、アプリケーション共有セッションで開く  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |音声ビデオ エッジ  <br/> |443  <br/> |50000 - 59999  <br/> |音声、ビデオ、アプリケーション共有セッションで開く  <br/> |
|STUN  <br/> |UDP  <br/> |音声ビデオ エッジ  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |音声、ビデオセッションで開く  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |音声ビデオ エッジ  <br/> |3478  <br/> |3478  <br/> |音声、ビデオセッションで開く  <br/> |

ポートとファイアウォールがエッジ サーバーの計画に関する詳細については、 [Skype ビジネス サーバー用にエッジ サーバー環境の要件](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)を参照してください。 「[Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md)」および「[プロトコル負荷の図](https://go.microsoft.com/fwlink/p/?LinkId=550989)」も参照してください。

## <a name="user-accounts-and-data"></a>ユーザー アカウントとデータ
<a name="BKMK_UserAccounts"> </a>

ハイブリッド展開では、ホームをオンラインにするすべてのユーザーする必要があります最初に作成、設置型展開で Active Directory ドメイン サービスのユーザー アカウントが作成されるようにします。 ビジネス、オンライン ユーザーの連絡先リストを移動するために Skype のユーザーを移動できます。

設置型展開と AAD の接続を使用してオンラインのテナント間でのユーザー アカウントを同期するときする必要がありますビジネスまたは Lync のユーザー、組織内のすべての Skype の AD のアカウントを同期する場合でも、ユーザーがオンラインに移動できません。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。

> [!IMPORTANT]
> すべてのユーザーの管理を含むユーザーがビジネスのオンラインでの設置と Skype との間に移動行う必要があります管理ツールのインストールされている最新のバージョンを使用します。 管理ツールは、既存のオンプレミスに展開して、インターネットにアクセスを接続するには別のサーバーにインストールしなければなりません。 [Csuser からの移動](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)、ビジネス オンラインの Skype をオンプレミス環境のユーザーを移動するコマンドレットは、社内設置型の展開に接続されている管理ツールから実行してください。 ユーザーの移動の詳細については、[ビジネス オンラインの Skype への設置型からユーザーを移動する](move-users-from-on-premises-to-skype-for-business-online.md)を参照してください。

ハイブリッド展開を計画する場合も、次のユーザーに関連する問題を考慮してください。

- **ユーザーの連絡先**ユーザーの Lync オンラインの連絡先の最大数は、250 です。 その番号以外のすべての連絡先は、Lync Online にアカウントが移動されたときにユーザーの連絡先リストから削除されます。

- **インスタント メッセージングとプレゼンス**ユーザーの連絡先リスト、グループ、およびアクセス制御リスト (Acl) は、ユーザー アカウントに移行されます。

- **会議データ、会議コンテンツ、およびスケジュールされたミーティング**このコンテンツは、ユーザー アカウントには移行されません。 ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。

## <a name="user-policies-and-features"></a>ユーザー ポリシーと機能
<a name="BKMK_UserPolicies"> </a>

- ハイブリッド環境では、ユーザーに対してインスタント メッセージングおよび会議のオンプレミスまたはオンラインでの使用を許可できますが、両方を同時に許可することはできません。

- **クライアントのサポート**一部のユーザーは、オンライン ビジネスの Skype を移動したとき、クライアントの新しいバージョンにすることがあります。 Office 通信 Server 2007 R2、ユーザーのオンライン ビジネスの Skype に移行する前に、ビジネスのサーバーまたは Lync Server 2013 プール、Skype を移動しなければなりません。

- **設置ポリシーおよび構成 (ユーザーではない)** オンラインと設置型のポリシーは、個別の構成を必要とします。 両方に適用されるグローバル ポリシーを設定することはできません。
