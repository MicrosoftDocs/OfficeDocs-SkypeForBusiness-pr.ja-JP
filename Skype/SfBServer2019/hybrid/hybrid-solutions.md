---
title: ハイブリッド ソリューションのビジネス用の Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/18/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ビジネス サーバー 2019 の Skype で利用可能なハイブリッド ・ ソリューションについて説明します。
ms.openlocfilehash: 2909f524d1b9984fe01700a89d1bf6dc1b70f100
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696227"
---
注意: 以下は 2015年からコピーし、進行中します。 [以下](#placeholder-topic-for-hybrid-solutions)その他の進行中のプレース ホルダーのコンテンツをご覧ください。


# <a name="skype-for-business-hybrid-solutions"></a>ハイブリッド ソリューションのビジネス用の Skype

Skype のビジネスのハイブリッド展開の計画に関する情報を検索します。 
  
このトピックでは、ビジネスに最適な構成の特定に役立つさまざまなハイブリッド構成について説明します。 次に、このトピックのリンク従って、関心のある構成についての詳細を読むことができます。 このトピックは、以下のセクションで構成されています。
  
- [Skype for Business ハイブリッド構成](hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Skype ビジネス オンラインに、既存のオンプレミス Skype のビジネス環境を追加します。](hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Office 365 の電話システム (クラウド PBX) を活用する](hybrid-solutions.md#BKMK_CloudPBX)
    
- [Exchange や SharePoint と統合する](hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [ハイブリッド環境の計画や構成のタスク](hybrid-solutions.md#BKMK_Tasks)
    
- [関連情報](hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Skype for Business ハイブリッド構成
<a name="BKMK_HybridConfigurations"> </a>

ビジネス用の Skype は、いくつかのハイブリッド構成をサポートします。 用に、既存のビジネスのオンライン設置型のビジネス環境に Skype は、Skype を追加、Exchange Online と SharePoint Online では、ビジネスの展開に、Skype を統合および Office 365 (クラウド PBX) の電話システムを利用できる、マイクロソフトのオンライン ビジネスの通話の制御、Skype で Office 365 のクラウド内のプライベート構内交換機 (PBX) 機能を有効にするための技術です。 
  
ハイブリッド展開のビジネス用の Skype では、ビジネス ソリューションを設置型の Skype でのオンライン ビジネス サービスの Skype を結合します。 組織内のサービスとしてのソフトウェアの管理スキルの構築を開始し、ビジネス ユーザー向けに、Skype を自分のペースでクラウドに移行できます。 クラウドをホームとするユーザーを利用して電話システムの Office 365 の設置公衆交換電話網 (PSTN) の接続性を維持しながら。
  
ビジネスのハイブリッド構成の Skype で、以下を留意してください。
  
- ユーザーは、オンプレミスにホストされる場合とオンラインにホストされる場合がありますが、同じセッション開始プロトコル (SIP) ドメイン (contoso.com など) を共有します。
    
- できますユーザーを移行する設置型のビジネス用の Skype から Skype をオンライン ビジネスの時間の経過と共に、スケジュールに。
    
- Exchange Online や SharePoint Online などの、別の Microsoft Office 365 アプリケーションと統合することができます。
    
- Exchange や SharePoint と統合することができます。
    
- Skype 会議ブロードキャストを活用することができます。
    
- PSTN 会議を活用することができます。
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Skype ビジネス オンラインに、既存のオンプレミス Skype のビジネス環境を追加します。
<a name="BKMK_HybridConnectivity"> </a>

Skype ビジネス サーバーとビジネス オンラインの Skype との間のハイブリッドの接続では、contoso.com などのドメインのユーザーが社内のビジネス サーバーと Skype の Skype を使用してオンライン ビジネスの間で分割を意味します。 一部のドメイン ユーザーはオンプレミスに所属し、その他のユーザーはオンラインに所属します。 Skype でオンライン ビジネスのハイブリッド、設置型の展開を構成し、作業中のディレクトリ同期を使用して、設置型およびオンライン ユーザーの同期を維持できます。 
  
次の図は、既存設置 Skype のビジネス環境において、ユーザーを自分のペースでクラウドに移行することに、オンライン ビジネスの Skype を追加する方法を示しています。
  
![Skype for Business ハイブリッド構成](../../sfbserver/media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
詳細については、[ビジネスのサーバーとビジネス オンラインまたはチームの Skype の Skype 間のハイブリッド接続を計画](plan-hybrid-connectivity.md)し、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Office 365 の電話システム (クラウド PBX) を活用する
<a name="BKMK_CloudPBX"> </a>

 Office 365 (クラウド PBX) の電話システムは、オンライン ビジネスの通話の制御、Skype で Office 365 のクラウド内のプライベート構内交換機 (PBX) 機能を有効にするための Microsoft のテクノロジです。 Office 365 の電話システムを利用すると、既存の PBX システムを Office 365 で提供される機能のセットと置き換えて、会社のクラウドと緊密に連携して生産性を向上させることができます。
  
Office 365 のハイブリッド ・ ソリューションの 2 つの電話システムの他は、マイクロソフトは、計画を呼び出すと、Office 365 の電話システムを提供しています: サービスの呼び出しの PSTN: クラウドをすべてソリューションの場合、オンプレミスのサーバーの展開を必要としません。 かどうかは、計画を呼び出すと、Office 365 の電話システムは、組織に最適なソリューションと可能性がありますを決定するには、[ソリューションを Office 365 に電話システム](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)を参照してください。
  
Office 365 のハイブリッド サービス提供では次の 2 つの電話システムがあります。  
  
- [Skype for Business Server 展開で提供されるオンプレミス接続を備えた Office 365 の電話システム](hybrid-solutions.md#BKMK_Server)
    
- [Skype for Business Server Cloud Connector エディションで提供されるオンプレミス接続を備えた Office 365 の電話システム](hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Skype for Business Server 展開で提供されるオンプレミス接続を備えた Office 365 の電話システム
<a name="BKMK_Server"> </a>

この構成は、PSTN のハイブリッドが変更されました。 ビジネス サーバー設置型の展開に、Skype で構成されます。 クラウドに置かれている組織内のユーザーはマイクロソフトのクラウドから PBX サービスを受信することができますが、PSTN への接続は、設置型の Skype でエンタープライズ VoIP ビジネス サーバーの展開の提供します。 
  
![Skype for Business Server 展開を備えたクラウド PBX](../../sfbserver/media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
この構成は、次のような場合に最適です。 
  
- PBX では、保持する必要のある一意の機能が提供されない。
    
- 国内通話プラン、Office 365 PSTN 通話サービスは所在地域で利用できない。
    
- ビジネス サーバー配置の既存の Lync または Skype があります。
    
詳細について[と Office 365 の電話システムの計画、設置型で Skype ビジネス サーバーの PSTN への接続](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)し、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムのユーザーを有効にする](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md)を参照してください。
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>Skype for Business Server Cloud Connector エディションで提供されるオンプレミス接続を備えた Office 365 の電話システム
<a name="BKMK_CCE"> </a>

この構成は、パッケージ化された一連の、オンプレミス PSTN 接続を実装する仮想マシンで構成されます。 ビジネス サーバー トポロジの場合、仮想化された環境で最小限の Skype を配布すると、クラウドに置かれている組織内のユーザーはマイクロソフトのクラウドから PBX サービスを受信することができますが、PSTN への接続は、既存のオンプレミス音声を通じて提供されます。インフラストラクチャです。 
  
![CloudPBXCloudConnectorEdition](../../sfbserver/media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
この構成は、次のような場合に最適です。
  
- PBX では、保持する必要のある一意の機能が提供されない。
    
- 国内通話プラン、Office 365 PSTN 通話サービスは所在地域で利用できない。
    
- ビジネス サーバーの展開、既存の Lync または Skype を必要はありません。
    
詳細については、 [Skype ビジネス クラウド コネクタ ・ エディションの計画](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)を参照してください。
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Exchange や SharePoint と統合する
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

ビジネスのハイブリッド構成で、Skype を使用すると、Exchange Online と SharePoint Online を含む他の Microsoft Office 365 アプリケーションと統合できます。
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype for Business Server と Exchange Online および SharePoint Online

ビジネス サーバーは、Exchange Online と SharePoint のオンラインでの Skype を統合するには、次の図に示すようにします。
  
![Skype for Business Server と Exchange Online および SharePoint Online](../../sfbserver/media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
ビジネス サーバーは、Exchange Online と SharePoint のオンラインでの Skype を統合すると、いくつかの利点があります。 以下を行えるようになります。
  
- ビジネス サーバー用には、Skype の完全な機能セットを使用します。
    
- PBX などの、既存のオンプレミスの電話機を利用する。
    
- 電子メールに Exchange Online を使用して、オンプレミスの電子メール サーバーとストレージの負荷を軽減する。
    
- グループ作業に SharePoint Online を使用して、オンプレミスの SharePoint サーバーを維持する負荷を軽減する。
    
- ビジネス、Exchange、および SharePoint を使用して Skype では、機能を含むユニファイド メッセージング (UM) Office 365 に統合されています。
    
詳細については、「[Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)」を参照してください。
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server と Skype for Business Online

次の図に示すように、オンライン ビジネスの Skype で Exchange Server を統合できます。
  
![Exchange と Skype for Business Online の統合](../../sfbserver/media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Skype でオンライン ビジネスの Exchange Server を統合すると、次の利点があります。
  
- 既存の Exchange インフラストラクチャを利用する。
    
- オンライン ビジネスのプレゼンス、IM、および会議の機能のための Skype を使用します。 
    
詳細については、「[Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)」を参照してください。
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>ハイブリッド環境の計画や構成のタスク
<a name="BKMK_Tasks"> </a>

ビジネス用の Skype では、展開を設計する方法に関係なく機能の豊富なセットを提供します。 選択するアーキテクチャにより、担当する IT 分野と、サブスクリプションを介してサポートのためにマイクロソフトに支払う内容が決まります。 組織に最適なアーキテクチャがどれであっても、常に独自に担当することになる、コアの分野が 5 つあります。
  
- **ネットワー キングと接続性**のネットワーク評価を実行することによって、または評価を行うパートナーと契約することでネットワークの容量およびファイアウォール、プロキシ サーバー、ゲートウェイ、および WAN リンクの可用性を確保します。
    
- **データ ・ ガバナンス&amp;著作権管理**- は、機密データを分類し、保護および監視の転送中には、格納されている任意の場所にいることを確認します。
    
- **クライアント エンドポイント**の設定、測定、データと資産にアクセスするために使用されているデバイスの最新のセキュリティ標準を適用します。
    
- **アカウント&amp;アクセス管理**- 通常アカウント アクティビティの場合、プロファイルを作成し、異常なアクティビティに通知します。
    
- **ID** - すべての ID に対して、ハードウェアで保護された資格情報か、複数要素の認証 (MFA) を使用します。
    
オンプレミス環境で実行するアーキテクチャのタスクに加えて、以下も行う必要があります。
  
- オンプレミス ID と Office 365 の統合を含む、ID 管理要件を計画して設計する。
    
- ネットワークのキャパシティと可用性を確保する。
    
- サード パーティの SSL 証明書を取得して、Office 365 のサービス内容のエンタープライズ セキュリティを提供する。
    
- Office 365 への接続に Internet Protocol バージョン 6 (IPv6) を使用するかどうかを決定する。
    
- 設置型とのビジネスでは、Exchange では、Skype のオンライン バージョンをどの程度の機能統合を決定し、SharePoint を希望します。 
    
- Office 365 からの要求に、どのプロキシ サーバー デバイスを使用するかを決定する。
    
フォローを実行する必要があります、Skype をビジネスのハイブリッド環境を実装する IT プロフェッショナルの作業。
  
- 有効にし、ビジネス オンラインの Skype での Microsoft Office 365 のテナントがある場合を確認します。
    
- ID 管理計画を実装する。 
    
- 内部および外部の DNS レコードとルーティングを計画して実装する。
    
- Office 365 IP アドレスと URL の要件向けにプロキシとファイアウォールを構成する。
    
- オンライン ビジネスの設定のユーザー アカウントと Skype を管理します。 
    
- 必要に応じてプロキシ サーバー デバイスを構成する。 
    
- Exchange Server と SharePoint のオンプレミス バージョンとオンライン　バージョンで機能の統合を構成する。
    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_MoreInfo"> </a>

詳しくは、次のリソースをご覧ください。
  
- [Microsoft クラウド IT アーキテクチャのリソース](https://aka.ms/clouditarch)
    
- [エンタープライズ アーキテクトのための Microsoft クラウド ID](https://docs.microsoft.com/en-us/office365/enterprise/microsoft-cloud-it-architecture-resources#identity)
    
- [Office 365 Enterprise向けに組織を準備する (英語)](https://aka.ms/O365EntPrep)
    
- [ビジネス オンラインまたはチームの業務サーバーの Skype と Skype との間のハイブリッドの接続を計画します。](plan-hybrid-connectivity.md)
    
- [Skype ビジネス サーバーとビジネス オンラインの Skype との間のハイブリッド接続を設定します。](configure-hybrid-connectivity.md)
    
- [Office 365 ソリューションの電話システム](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
このトピックのポスター バージョンをダウンロードする場合は、以下にアクセスしてください。
  
- [Skype for Business Architectural Models (pdf、英語)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)
    
- [Skype for Business Architectural Models (Visio、英語)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)
    

### <a name="placeholder-topic-for-hybrid-solutions"></a>ハイブリッド ソリューション用のプレース ホルダー トピック 

進行中.


「ハイブリッド音声」という用語に馴染みがある場合もあるかもしれません。これは、クラウドに所属しているユーザーに機能を提供するオンプレミスの音声トランクのことです。 ハイブリッド音声によって、オンプレミスの音声構成を保持しながらクラウドに移行できます。 Skype for Business Server がすでに展開されている場合、ハイブリッド音声を有効にするために最初に行う手順は、分割ドメイン環境の設定となります。 
  
たとえば、会社が最低限の PBX を必要とする組織をサポートする大規模な携帯電話番号フィールドには音声ですが、多くのスマート フォンを使用します。 このような場合、これらのユーザーをクラウドに移動して、Office 365 における Microsoft の電話システム (クラウド PBX) を利用することが考えられます。 また、会社、設置型の PBX の一部としてコミュニケーション センターの高度で複雑なソフトウェアを必要とする大規模な設置型のコール センターの場合は、施設内でこれらのユーザーのままにすることもできます。 オンライン、オンプレミスに所属するいずれのユーザーも、オンプレミス展開によって PSTN 接続を利用できます。
  
次の図に Skype for Business のハイブリッド音声展開を示します。
  
![クラウド PBX での SfB 分割ドメイン](../../sfbserver/media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
ハイブリッド音声ソリューション ビジネス サーバーの展開について、Skype での設定に関する詳細については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)を参照してください。 
  
統合するためのハイブリッド展開を構成することも、オンプレミス Exchange、SharePoint、または、Microsoft Office 365 アプリケーションと Exchange Online と SharePoint Online を含みます。 Cloud Connector エディションを使用して、フル機能の Skype for Business Server 展開を必要としないハイブリッド音声ソリューションを設定することもできます。 ハイブリッド ソリューションのビジネスおよび計画のためのすべての Skype の詳細については、クラウドへの移行では、[ハイブリッド ソリューションのビジネス用の Skype](hybrid-solutions.md)を参照してください。


## <a name="exchange-co-existence"></a>Exchange との共存
<a name="BKMK_Exchange"> </a>

Exchange との共存をサポートする場合は、以下の点に留意してください。
  
- Exchange のオンライン ホーム ビジネスのためのユーザーの Skype を移動する前にユーザーのメールボックスを移動することをお勧めします。
    
- オンプレミスに Exchange のメールボックスがあるユーザーについては、次の既知の制限付きでサポートされます。
    
  - クライアントのサインオン: ユーザーは、SfB クライアントのサインオン中に 2 回サインオンする必要がある場合があります。
    
  - サーバー側会話の履歴、アーカイブ、統合連絡先ストア、HighRes 写真が Exchange 2013 以降を必要とし、サーバー間の通信に OAuth サーバーを有効にする必要があります。 詳細については、[管理サーバーからサーバーへの認証 (OAuth) とビジネス サーバー 2015 の Skype のパートナーのアプリケーション](https://technet.microsoft.com/en-us/library/jj204817.aspx)を参照してください。
    
オンプレミスとオンラインのさまざまな組み合わせに関するサポートの条件および制限を含む、Exchange Server との共存に関する詳細については、[Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) の「[機能のサポート](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」を参照してください。



**用語集**

ou は、次のセクションでの Active Directory の構成の詳細について学習します。 その前に、以下の図で使用され、ハイブリッド接続のトピックでも頻繁に使用される用語と頭字語を示します。
  
- PSTN - 公衆交換電話網
    
- PBX - 構内交換機システム
    
- 電話システム - Microsoft のクラウド PBX 電話システムによるサービス
    
- トランクの Pbx を接続するのには、PSTN テレフォニーの回線-トランクは、セッション開始プロトコル (SIP) を使用して可能性があります: インターネット プロトコル (VoIP) ボイスを A、または時分割多重 (TDM) の以前のテクノロジ 
    
- SBC - セッション ボーダー コントローラー - テレフォニー ネットワークにおいてファイアウォールおよびルーターとして機能するデバイス。 たとえば、セキュリティ、接続、相互運用性、およびサービス品質を提供します。 
    
- PSTN ゲートウェイ - テレフォニー ネットワークでルーターとして機能するデバイスで、セキュリティと NAT 通過以外の、SBC が実行できるほとんどのことを実行できます。
    
次の図は、ビジネスの「ドメインの分割」のハイブリッド構成 Skype を示しています。 ユーザー A および B はオンラインに所属していますが、オンプレミスのユーザーによって検出可能となっています。ユーザー C および D はオンプレミスに所属していますが、オンライン ユーザーによって検出可能となっています。
  

