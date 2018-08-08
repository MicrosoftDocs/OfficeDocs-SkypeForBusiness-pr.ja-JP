---
title: Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: '概要: このトピックでは、Skype for Business Server と Skype for Business Online 間でハイブリッド接続を計画する方法を説明します。 多くの Skype for Business ハイブリッド ソリューションを展開する上で、ハイブリッド接続の設定は最初に行う手順となります。'
ms.openlocfilehash: 2cd4c66ebd36542fa90cb8b8bcd0aa88da0d8df0
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2018
ms.locfileid: "21145366"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する
 
**概要:** このトピックでは、Skype for Business Server と Skype for Business Online 間でハイブリッド接続を計画する方法を説明します。 多くの Skype for Business ハイブリッド ソリューションを展開する上で、ハイブリッド接続の設定は最初に行う手順となります。
  
ここで、概要を説明し、インフラストラクチャについて説明し、システム要件の間、既存のハイブリッド接続を構成する必要があります設置 Skype ビジネス サーバー配置の設置型で、作成したユーザーにActive Directory、およびオンライン ビジネス用の Skype です。 
  
このトピックには次のセクションが含まれます。
  
- [概要](plan-hybrid-connectivity.md#BKMK_Overview)
    
- [インフラストラクチャの要件](plan-hybrid-connectivity.md#BKMK_Infrastructure)
    
- [マルチ フォレストのサポート](plan-hybrid-connectivity.md#BKMK_MultiForest)
    
- [Exchange との共存](plan-hybrid-connectivity.md#BKMK_Exchange)
    
- [管理者の資格情報](plan-hybrid-connectivity.md#BKMK_Credentials)
    
- [Skype for Business Online PowerShell](plan-hybrid-connectivity.md#BKMK_PowerShell)
    
- [Skype for Business のクライアント サポート](plan-hybrid-connectivity.md#BKMK_ClientSupport)
    
- [トポロジ要件](plan-hybrid-connectivity.md#BKMK_Topology)
    
- [フェデレーション許可/禁止の一覧の要件](plan-hybrid-connectivity.md#BKMK_Federation)
    
- [DNS の設定](plan-hybrid-connectivity.md#BKMK_DNS)
    
- [ファイアウォールの考慮事項](plan-hybrid-connectivity.md#BKMK_Firewall)
    
- [ポートとプロトコルの要件](plan-hybrid-connectivity.md#BKMK_Ports)
    
- [ユーザー アカウントとデータ](plan-hybrid-connectivity.md#BKMK_UserAccounts)
    
- [ユーザー ポリシーと機能](plan-hybrid-connectivity.md#BKMK_UserPolicies)
    
このトピックを参照した後、展開、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)を参照してくださいする準備ができました。 展開のトピックでは、オンプレミス展開と Skype for Business Online との間でハイブリッド接続を設定するための手順について説明しています。
  
(Lync Server 2013、ハイブリッドの Lync Server 2010 展開を構成する方法の詳細については、 [Lync Server 2013 ハイブリッド](https://go.microsoft.com/fwlink/p/?LinkId=617360)を参照してください)。
  
## <a name="overview"></a>概要
<a name="BKMK_Overview"> </a>

ハイブリッド ソリューションによって、スケジュールとビジネス ニーズを基に、ユーザーをクラウドに移動できます。 このトピックでは、Skype for Business Server のオンプレミス展開と Skype for Business Online との間のハイブリッド接続を中心に説明します。 この接続によって、ユーザーの所属をオンプレミスやオンラインに設定できます。
  
この種類の配置は「ドメインの分割」と呼ば-間を使用して Skype 社内のビジネス サーバーと Skype のオンライン ビジネス次ように分割は、contoso.com などドメイン ユーザーを意味します。
  
- オンプレミスに所属するユーザーは、オンプレミスの Skype for Business サーバーと対話します
    
- オンラインに所属するユーザーは、Skype for Business Online サービスと対話します
    
- いずれの環境の場合も、ユーザーは、インスタント メッセージングの使用、電話会議への参加、VoIP 通話などによって、互いに共同作業できます
    
- オンプレミスのディレクトリを Office 365 と同期させる場合は Azure Active Directory Connect が使用されます
    
オンプレミスの Active Directory は優先されるため、次のことを実行してオンプレミスおよびオンラインのユーザーが相互に検出できるようにする必要があります。
  
- すべてのユーザーは、最初に、オンプレミスの Active Directory 内に作成し、Azure AD に同期する必要があります。 
    
- オンプレミスに所属していて Skype for Business を利用するユーザーについては、Skype for Business オンプレミスに対して有効化する必要があります。
    
- オンプレミスに所属しているのに Skype Meeting Broadcast などのオンライン機能を利用したいユーザーについては、Skype for Business Online プラン 2 のライセンスを割り当てる必要があります。
    
- Skype for Business Online に所属していて、アカウントが Azure AD に同期されたユーザーについては、Skype for Business Online プラン 2 のライセンスを割り当てる必要があります。 
    
- ライセンスが割り当てられた Sype for Business Online ユーザーについては、Skype for Business またはオンプレミスの Enterprise Voice を有効にする必要があります。 詳細については、[社内設置型のエンタープライズ VoIP のユーザーを有効にする](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)を参照してください。 ハイブリッド音声の要件の詳細については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)を参照してください。
    
Active Directory の設定の詳細については、この後のセクションで説明します。 その前に、以下の図で使用され、ハイブリッド接続のトピックでも頻繁に使用される用語と頭字語を示します。
  
- PSTN - 公衆交換電話網
    
- PBX - 構内交換機システム
    
- 電話システム - Microsoft のクラウド PBX 電話システムによるサービス
    
- トランクの Pbx を接続するのには、PSTN テレフォニーの回線-トランクは、セッション開始プロトコル (SIP) を使用して可能性があります: インターネット プロトコル (VoIP) ボイスを A、または時分割多重 (TDM) の以前のテクノロジ 
    
- SBC - セッション ボーダー コントローラー - テレフォニー ネットワークにおいてファイアウォールおよびルーターとして機能するデバイス。 たとえば、セキュリティ、接続、相互運用性、およびサービス品質を提供します。 
    
- PSTN ゲートウェイ - テレフォニー ネットワークでルーターとして機能するデバイスで、セキュリティと NAT 通過以外の、SBC が実行できるほとんどのことを実行できます。
    
次の図は、ビジネスの「ドメインの分割」のハイブリッド構成 Skype を示しています。 ユーザー A および B はオンラインに所属していますが、オンプレミスのユーザーによって検出可能となっています。ユーザー C および D はオンプレミスに所属していますが、オンライン ユーザーによって検出可能となっています。
  
![SfB ハイブリッド接続 - 分割ドメイン](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)
  
「ハイブリッド音声」という用語に馴染みがある場合もあるかもしれません。これは、クラウドに所属しているユーザーに機能を提供するオンプレミスの音声トランクのことです。 ハイブリッド音声によって、オンプレミスの音声構成を保持しながらクラウドに移行できます。 Skype for Business Server がすでに展開されている場合、ハイブリッド音声を有効にするために最初に行う手順は、分割ドメイン環境の設定となります。 
  
たとえば、会社が最低限の PBX を必要とする組織をサポートする大規模な携帯電話番号フィールドには音声ですが、多くのスマート フォンを使用します。 このような場合、これらのユーザーをクラウドに移動して、Office 365 における Microsoft の電話システム (クラウド PBX) を利用することが考えられます。 また、会社、設置型の PBX の一部としてコミュニケーション センターの高度で複雑なソフトウェアを必要とする大規模な設置型のコール センターの場合は、施設内でこれらのユーザーのままにすることもできます。 オンライン、オンプレミスに所属するいずれのユーザーも、オンプレミス展開によって PSTN 接続を利用できます。
  
次の図に Skype for Business のハイブリッド音声展開を示します。
  
![クラウド PBX での SfB 分割ドメイン](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
ハイブリッド音声ソリューション ビジネス サーバーの展開について、Skype での設定に関する詳細については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)を参照してください。 
  
統合するためのハイブリッド展開を構成することも、オンプレミス Exchange、SharePoint、または、Microsoft Office 365 アプリケーションと Exchange Online と SharePoint Online を含みます。 Cloud Connector エディションを使用して、フル機能の Skype for Business Server 展開を必要としないハイブリッド音声ソリューションを設定することもできます。 ハイブリッド ソリューションのビジネスおよび計画のためのすべての Skype の詳細については、クラウドへの移行では、[ハイブリッド ソリューションのビジネス用の Skype](skype-for-business-hybrid-solutions.md)を参照してください。
  
## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
<a name="BKMK_Infrastructure"> </a>

Skype for Business Server と Skype for Business Online との間でハイブリッド接続を実装および展開するには、次の項目を環境に構成する必要があります。
  
- 1 つ設置 Skype のビジネス サーバーまたはサポートされているトポロジに展開されている Lync Server の展開です。 このトピックでは、[トポロジの要件](plan-hybrid-connectivity.md#BKMK_Topology)を参照してください。
    
    > [!NOTE]
    > オンプレミス環境に存在するすべての SIP ドメインは、Office 365 のテナントと逆でも存在する必要があります。 のみいくつかの SIP ドメインをオンラインができませんし、いくつかのドメインの設置型のみです。 それ以外の場合、プレゼンス、IM、およびその他の機能が正しく動作しません。
    
- 有効にし、ビジネス オンラインの Skype での Microsoft Office 365 テナントです。 
    
    > [!NOTE]
    > オンプレミス展開があるハイブリッド構成には、1 つのテナントしか使用できません。 
  
- サーバー 2015 のビジネス管理ツールの Skype です。 (Lync Server 2013 または Lync Server 2010 を使用する場合することができます、Lync Server 2013 管理ツールを使用します。 について詳細については、「 [Lync Server 2013 ハイブリッド](https://go.microsoft.com/fwlink/p/?LinkId=617360))
    
- オンプレミスのディレクトリを Office 365と同期させる Azure Active Directory Connect。 詳細については、 [Azure Active Directory と Active Directory の接続](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)を参照してください。
    
    ユーザーがオンプレミスで使用するものと同じログイン資格情報を使用できるように Office 365 でのシングル サインオンをサポートする場合、Azure Active Directory (AAD) Connect のパスワード同期機能を使用できます。 また、Office 365 でのシングル サインオンに Active Directory フェデレーション サービス (AD FS) を使用することもできます。 
    
- オンプレミスの Skype for Business 展開と Office 365 テナントとの間の有効なフェデレーション。 フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。 詳細については、[オンライン ビジネスの Skype でフェデレーションを構成する](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)を参照してください。
    
- 有効な、共有されたセッション開始プロトコル (SIP) アドレス空間。 SIP アドレスは、電話番号や電子メール アドレスに似ている、ネットワーク上の各ユーザーの一意の識別子です。 オンライン ビジネスのユーザーを設置から Skype に移動しようとすると、前に、社内設置型展開と共有のセッション開始プロトコル (SIP) アドレス空間を共有するのには、Office 365 のテナントを構成する必要があります。 詳細については、[オンライン ビジネスの Skype でフェデレーションを構成する](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)を参照してください。
    
## <a name="multi-forest-support"></a>マルチ フォレストのサポート
<a name="BKMK_MultiForest"> </a>

ユーザーは、次の要件が満たされれば、別のフォレストで Skype for Business の機能にアクセスできます。
  
- ユーザーが、Skype for Business をホストするフォレストに適切に同期されている。ハイブリッド構成において、これはユーザーが無効化されたユーザー オブジェクトとして同期される必要があることを意味します。
    
- Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。
    
ハイブリッドの複数のフォレスト シナリオの詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)を参照してください。
  
## <a name="exchange-co-existence"></a>Exchange との共存
<a name="BKMK_Exchange"> </a>

Exchange との共存をサポートする場合は、以下の点に留意してください。
  
- Exchange のオンライン ホーム ビジネスのためのユーザーの Skype を移動する前にユーザーのメールボックスを移動することをお勧めします。
    
- オンプレミスに Exchange のメールボックスがあるユーザーについては、次の既知の制限付きでサポートされます。
    
  - クライアントのサインオン: ユーザーは、SfB クライアントのサインオン中に 2 回サインオンする必要がある場合があります。
    
  - サーバー側会話の履歴、アーカイブ、統合連絡先ストア、HighRes 写真が Exchange 2013 以降を必要とし、サーバー間の通信に OAuth サーバーを有効にする必要があります。 詳細については、[管理サーバーからサーバーへの認証 (OAuth) とビジネス サーバー 2015 の Skype のパートナーのアプリケーション](https://technet.microsoft.com/en-us/library/jj204817.aspx)を参照してください。
    
Exchange Server との共存の詳細については、サポートを含む条件とさまざまな組み合わせでの制限の設置とオンラインで参照してください[ビジネスとの交換用 Skype を統合する計画](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)の[サポート機能](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。
  
## <a name="administrator-credentials"></a>管理者の資格情報
<a name="BKMK_Credentials"> </a>

管理者の資格情報を提供するメッセージが表示されたらを使用してユーザー名とパスワード管理者アカウントに、Office 365 テナントのです。 フェデレーション、ディレクトリ同期、シングル サインオン、および移動ユーザーが Skype のオンライン ビジネスの Azure Active Directory を構成するときにも、これらの資格情報を使用します。
  
## <a name="skype-for-business-online-powershell"></a>Skype for Business Online PowerShell
<a name="BKMK_PowerShell"> </a>

管理者には、オンライン ビジネス、オンライン ビジネスのユーザー アカウントに対して、Skype の Skype を管理するために Windows PowerShell を使用する機能があるようになりました。 これを行うには、まずダウンロードして、Microsoft ダウンロード センターからオンライン コネクタ モジュールをビジネス用の Skype をインストールします。 ダウンロードの詳細については、インストール、およびコネクタ モジュールのオンライン ビジネス、およびビジネスのオンラインでの Skype を管理するために Windows PowerShell を使用しての詳細については、Skype を使用するを参照してください[Skype のビジネスを管理するために Windows PowerShell を使用します。オンライン](https://technet.microsoft.com/library/dn362831.aspx)です。 
  
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
    
ホーム ユーザー、組織内を決定する前に、クライアントのサポート、さまざまな Skype のビジネスのサーバーの構成を決定する[ビジネス用の Skype のデスクトップ クライアントの機能の比較](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)を表示します。 以下の項目もご覧ください。
  
- [クライアントおよびデバイスの計画](../plan-your-deployment/clients-and-devices/clients-and-devices.md)
    
- [Skype for Business のモバイル クライアント機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)
    
## <a name="topology-requirements"></a>トポロジ要件
<a name="BKMK_Topology"> </a>

Skype でオンライン ビジネスのハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかである必要があります。
  
- ビジネス サーバー 2015 の Skype を実行しているすべてのサーバーとサーバー 2015 のビジネス展開するための Skype です。
    
- Lync Server 2013 を実行しているすべてのサーバーに Lync Server 2013 展開します。
    
    ハイブリッド音声接続では、フェデレーション エッジとして指定されるエッジ サーバーは Skype for Business 2015 である必要があり、エッジにはバックエンドの Skype for Business Server も必要となります。 ユーザーのいないプールを持つことができます。 
    
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

許可されたドメイン] ボックスの一覧には、構成されているパートナー エッジ完全修飾ドメイン名 (FQDN) を持つドメインが含まれています。 これらは、許可されたパートナー サーバー ordirect のフェデレーション パートナーと呼ばれます。 開いているフェデレーションと終了と呼ばれるパートナー探索 andallowed パートナー ドメイン リストでは、それぞれ、設置型展開でフェデレーションの違いを理解する必要があります。
  
ハイブリッド展開を正しく構成するには、次の必要条件を満たす必要があります。
  
- オンプレミス展開と Office 365 テナントでドメイン マッチングの構成を同一にする必要があります。オンプレミス展開でパートナーの検出が有効になっている場合、オンライン テナントではオープン フェデレーションを有効にする必要があります。パートナーの検出が無効になっている場合、オンライン テナントではクローズド フェデレーションを構成する必要があります。
    
- オンプレミス展開における禁止ドメインの一覧はオンライン テナントの禁止ドメインの一覧と正確に一致する必要があります。
    
- オンプレミス展開における許可ドメインの一覧はオンライン テナントの許可ドメインの一覧と正確に一致する必要があります。
    
- オンラインのテナントは、コントロール パネルのオンライン ビジネスを Skype を使用して構成されているため、外部との連絡には、フェデレーションを有効にする必要があります。
    
## <a name="dns-settings"></a>DNS の設定
<a name="BKMK_DNS"> </a>

ハイブリッド展開用の DNS レコードを作成するには、外部の DNS レコードをビジネスのすべての Skype はオンプレミス インフラストラクチャを指し示します。 必要な DNS レコードの詳細については、 [Skype のビジネス サーバー 2015 の DNS の要件](../plan-your-deployment/network-requirements/dns.md)を参照してください。
  
さらに、次の表で説明している DNS 解決が使用しているオンプレミス展開で機能することを確認する必要があります。
  
|DNS レコード  <br/> |解決方法  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls._tcp の DNS SRV レコードです。\<sipdomain.com\>サポートされているすべての SIP ドメインがアクセス エッジの外部 IP(s) に解決するため  <br/> |エッジ サーバー  <br/> |ハイブリッド展開でフェデレーション通信を有効にする。オンプレミスとオンラインで分割される SIP ドメイン用のフェデレーション トラフィックのルートをエッジ サーバーで認識している必要があります。  <br/> ユーザー名のドメインと SRV レコードの間で一致する厳密な DNS 名を使用する必要があります。  <br/> |
|エッジ Web 会議サービス FQDN の DNS A レコード、たとえば、webcon.contoso.com は Web 会議のエッジ外部 IP に解決される  <br/> |ユーザーのコンピューターが社内ネットワークに接続されています。  <br/> |オンライン ユーザーを有効にして、オンプレミスのホストされた会議でのコンテンツを提供または表示する。コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモがあります。  <br/> |
   
所属する組織での DNS の構成方法によっては、内部 DNS 解決をこれらのレコードに適用するために、対応する SIP ドメインに対して組織内でホストする DNS ゾーンにこれらのレコードを追加する必要があります。

[!NOTE] _sipfederationtls._tcp。\<sipdomain.com\>からエッジ サーバーの SRV レコードの解決は、ハイブリッド構成に必要な。 エッジ サーバーがこれらのレコードを解決できない場合、オンプレミスのユーザーは、プレゼンスを参照するか、オンラインのユーザーと通信することはできません。

## <a name="firewall-considerations"></a>ファイアウォールの考慮事項
<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。
  
Microsoft Online Services のデータ ・ センターの場所、によって、ワイルドカード ドメイン名に基づいて接続を許可するのには、ネットワークのファイアウォール デバイスを構成する必要がありますも (からのすべてのトラフィックは、 \*. outlook.com)。 組織のファイアウォールはワイルドカードの名前の構成をサポートしていない場合は、許可したい IP アドレスの範囲、指定されたポートを手動で確認する必要があります。
  
詳細については、 [Office 365 の Url と IP アドレスの範囲](https://go.microsoft.com/fwlink/p/?LinkId=252942)を参照してください。
  
## <a name="port-and-protocol-requirements"></a>ポートとプロトコルの要件
<a name="BKMK_Ports"> </a>

内部通信に必要なポートのほかに、次のポートも構成して、ハイブリッド接続を有効にする必要があります。
  

|**プロトコル**|**TCP または UDP**|**発信元 IP アドレス**|**送信先 IP アドレス**|**発信元ポート**|**送信先ポート**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |アクセス エッジ  <br/> |Office 365  <br/> |任意  <br/> |5061  <br/> |信号  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |アクセス エッジ  <br/> |任意  <br/> |5061  <br/> |信号  <br/> |
|STUN  <br/> |TCP  <br/> |音声ビデオ エッジ  <br/> |Office 365  <br/> |50000 - 59999  <br/> |443  <br/> |音声、ビデオ、アプリケーション共有セッションで開く  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |音声ビデオ エッジ  <br/> |50000 - 59999  <br/> |443  <br/> |音声、ビデオ、アプリケーション共有セッションで開く  <br/> |
|STUN  <br/> |UDP  <br/> |音声ビデオ エッジ  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |音声、ビデオセッションで開く  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |音声ビデオ エッジ  <br/> |3478  <br/> |3478  <br/> |音声、ビデオセッションで開く  <br/> |
   
ポートとファイアウォールがエッジ サーバーの計画に関する詳細については、 [Skype のビジネス サーバー 2015 でエッジ サーバー環境の要件](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)を参照してください。 [サーバーのポートとプロトコルの要件](../plan-your-deployment/network-requirements/ports-and-protocols.md)と[プロトコルの負荷の図](http://go.microsoft.com/fwlink/p/?LinkId=550989)も参照ください。
  
## <a name="user-accounts-and-data"></a>ユーザー アカウントとデータ
<a name="BKMK_UserAccounts"> </a>

ハイブリッド展開では、オンライン ホームを使用するすべてのユーザー必要があります最初に作成、設置型展開で Active Directory ドメイン サービスのユーザー アカウントが作成されるようにします。 ビジネス、オンライン ユーザーの連絡先リストを移動するために Skype のユーザーを移動できます。
  
設置型展開と AAD の接続を使用してオンラインのテナント間でのユーザー アカウントを同期するときする必要がありますビジネスまたは Lync のユーザー、組織内のすべての Skype の AD のアカウントを同期する場合でも、ユーザーがオンラインに移動できません。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。
  
> [!IMPORTANT]
> すべてのユーザーの管理を含むユーザーがビジネスのオンラインでの設置と Skype との間に移動行う必要があります管理ツールのインストールされている最新のバージョンを使用します。 管理ツールは、既存のオンプレミスに展開して、インターネットにアクセスを接続するには別のサーバーにインストールしなければなりません。 [Csuser からの移動](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)、ビジネス オンラインの Skype をオンプレミス環境のユーザーを移動するコマンドレットは、社内設置型の展開に接続されている管理ツールから実行してください。 ユーザーの移動の詳細については、[ビジネス オンラインの Skype への設置型からユーザーを移動する](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md)を参照してください。 
  
> [!IMPORTANT]
> Office 365 のオンライン ポータルを使用してユーザーを作成した場合、ユーザー アカウントはオンプレミスの Active Directory と同期されず、ユーザーはオンプレミスの Active Directory には存在しません。 オンライン テナントでユーザーを作成済みで、オンプレミス展開を使用してハイブリッドを構成する場合は、「オンラインからオンプレミスへのユーザーの移動」を参照してください。 
  
> [!NOTE]
> 設置型展開で有効になっていないビジネス オンラインの Skype の有効なユーザーを持っているオンライン ビジネスのお客様に、Skype で現在開いている場合は、[ビジネス上でオンラインに設置型の Skype のユーザーの移動](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)を参照してください。 
  
また、ハイブリッド展開を計画する場合は、次のユーザー関連の問題も考慮する必要があります。
  
- **ユーザーの連絡先**ユーザーの Lync オンラインの連絡先の最大数は、250 です。 その番号以外のすべての連絡先は、Lync Online にアカウントが移動されたときにユーザーの連絡先リストから削除されます。
    
- **インスタント メッセージングとプレゼンス**ユーザーの連絡先リスト、グループ、およびアクセス制御リスト (Acl) は、ユーザー アカウントに移行されます。
    
- **会議データ、会議コンテンツ、およびスケジュールされたミーティング**このコンテンツは、ユーザー アカウントには移行されません。 ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。
    
## <a name="user-policies-and-features"></a>ユーザー ポリシーと機能
<a name="BKMK_UserPolicies"> </a>

- ハイブリッド環境では、ユーザーに対してインスタント メッセージングおよび会議のオンプレミスまたはオンラインでの使用を許可できますが、両方を同時に許可することはできません。
    
- **クライアントのサポート**一部のユーザーは、オンライン ビジネスの Skype を移動したとき、クライアントの新しいバージョンにすることがあります。 Office 通信 Server 2007 R2、ユーザーのオンライン ビジネスの Skype に移行する前に、ビジネスのサーバーまたは Lync Server 2013 プール、Skype を移動しなければなりません。
    
- **設置ポリシーおよび構成 (ユーザーではない)** オンラインと設置型のポリシーは、個別の構成を必要とします。 両方に適用されるグローバル ポリシーを設定することはできません。
    

