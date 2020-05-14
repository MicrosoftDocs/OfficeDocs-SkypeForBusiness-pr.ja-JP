---
title: Skype for Business Cloud Connector エディションの計画
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Skype for Business Cloud Connector エディション、電話システム (クラウド PBX) でオンプレミスの PSTN 接続を実装するパッケージ化された仮想マシン (Vm) のセットの情報を確認できます。
ms.openlocfilehash: d2b7f4203da082112b846cc3f12f57dd7758fc82
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220087"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Skype for Business Cloud Connector エディションの計画

Skype for Business Cloud Connector エディション、電話システム (クラウド PBX) でオンプレミスの PSTN 接続を実装するパッケージ化された仮想マシン (Vm) のセットの情報を確認できます。

既存の Lync Server または Skype for Business Server をまだ持っていない場合は、Cloud Connector Edition が組織に適したソリューションになることがあります。 お客様のビジネスに適した電話システムソリューションについて調査している場合は、「 [Microsoft テレフォニーソリューション](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)」を参照してください。

このドキュメントでは、Cloud Connector edition の要件とサポートされるトポロジについて説明し、Cloud Connector エディションの展開の計画に役立てることができます。 Cloud Connector 環境を構成する前に、このトピックを必ずお読みください。 Cloud Connector エディションを展開および構成する準備ができたら、「 [configure and Manage Skype For Business Cloud Connector edition](configure-skype-for-business-cloud-connector-edition.md)」を参照してください。

Cloud Connector Edition 2.1 を使用できるようになりました。 2.1 にまだアップグレードしていない場合は、「 [Cloud Connector の新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)」を参照してください。 インストールファイルは、で入手でき [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) ます。

> [!NOTE]
> Microsoft は、新しいバージョンのリリース後、60日間、Cloud Connector Edition の以前のバージョンをサポートしています。 Microsoft は、2.1 のリリース後、60日間、バージョン2.0.1 をサポートして、アップグレードの時間を確保します。 2.0.1 以前のすべてのバージョンはサポートされなくなりました。

Cloud Connector エディションは、電話システムでオンプレミスの PSTN 接続を実装するパッケージ化された仮想マシン (Vm) のセットで構成されるハイブリッド製品です。 最小限の Skype for Business Server トポロジを仮想化環境に展開することで、クラウドに所属している組織内のユーザーは、Microsoft クラウドから PBX サービスを受けることができますが、既存のオンプレミス音声インフラストラクチャを使用して PSTN 接続が提供されます。

![クラウド PBX を Skype for Business のオンプレミス展開に接続するクラウド PBX ゲートウェイを示しているトポロジ図。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Cloud Connector を使用すると、電話システムサービスを既存のテレフォニー環境 (PBX、アナログデバイス、コールセンターなど) と統合できるため、既存のテレフォニーソリューションから電話システムへの段階的な移行を実装できます。

たとえば、会社に、電話システムが提供しない特定の機能を備えた高度なコールセンターがあるとします。 通話センターのユーザーに既存のソリューションを使用したまま、他のユーザーを電話システムに移動することを選択できます。

Cloud Connector は、オンプレミスとオンラインのユーザー間のルーティングを提供し、独自の PSTN プロバイダーを電話システムで使用することを選択できます。

Cloud Connector エディションの展開を計画する場合は、次の点を考慮してください。

- Cloud Connector を使用してクラウド音声ソリューションを利用するには、電話システムを含む Microsoft 365 または Office 365 組織にサインアップする必要があります。 Microsoft 365 または Office 365 組織がまだない場合は、ここでサインアップする方法について説明します。 [microsoft 365 For Business](https://products.office.com/business/office)。 Skype for Business Online を含むプランにサインアップする必要があることに注意してください。

- Skype for Business Online サービスを使用して Cloud Connector アプライアンスを登録し、さまざまなコマンドレットを実行するには、Cloud Connector 2.0 以降を使用するには、Skype for Business テナント管理者権限を持つ専用の Microsoft 365 または Office 365 アカウントが必要です。 2.0 より前の Cloud Connector のバージョンでは、テナント全体管理者権限を持つ専用の Microsoft 365 または Office 365 アカウントが必要です。

- Cloud Connector では、完全なオンプレミスの Skype for Business Server 展開は必要ありません。

    現時点では、Cloud Connector は Lync または Skype for Business のオンプレミスサーバーと共存できません。 既存の Lync または Skype for Business ユーザーを Microsoft 365 に移行し、オンプレミステレフォニーをユーザーに提供する場合は、既存の Skype for Business Server 展開を使用して、オンプレミス接続を備えた電話システムを検討してください。 詳細については、「 [plan Your Phone system (CLOUD PBX)」ソリューション](plan-your-phone-system-cloud-pbx-solution.md)を参照してください。また、[オンプレミスの PSTN 接続を備えた電話システムを Skype for Business Server で計画](plan-phone-system-with-on-premises-pstn-connectivity.md)します。

- 以前の Skype for Business または Lync Server を展開していて、スキーマを拡張した場合は、環境からすべての Skype for Business または Lync Server コンポーネントを削除している限り、クラウドコネクタ展開のスキーマをクリーンアップする必要はありません。

- ユーザーはオンラインに所属しています。

- 組織でディレクトリ同期 (DirSync) が構成されている場合は、ハイブリッド音声に対して計画されているユーザーのすべてのアカウントを、まずオンプレミスの展開に作成してから、クラウドに同期する必要があります。

- 必要に応じて、現在の PSTN キャリアを維持することができます。

- Cloud Connector でホストされているユーザーにダイヤルイン会議を提供する場合は、Microsoft からの電話会議サービスへの通話に、PSTN 会議のライセンスまたは支払いを購入することができます。

- 通話のエスカレーションにも、電話会議のライセンス (または [お支払いに応じて支払う]) が必要です。 Skype for Business ユーザーが外部 PSTN ユーザーからの通話を受信し、その通話に1人以上の参加者を追加する (電話を会議にエスカレートする) 必要がある場合、エスカレーションは Microsoft 電話会議サービスを介して実行されます。

- Cloud Connector 2.0 以降がメディアバイパスをサポートするようになりました。 メディアバイパスを使用すると、クライアントはメディアを公衆交換電話網 (PSTN) の次ホップに直接送信できます。ゲートウェイまたはセッションボーダーコントローラー (SBC) を使用して、Cloud Connector Edition コンポーネントをメディアパスから削除します。 詳細については、 [Cloud Connector エディションの「Plan for media バイパス](plan-for-media-bypass-in-cloud-connector-edition.md)」を参照してください。

- Cloud Connector 2.1 以降では、Operations Management Suite (OMS) を使用したクラウドコネクタの監視をサポートしています。 詳細については、「 [Operations Management Suite を使用してクラウドコネクタを監視する (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) 」を参照してください。

- Cloud Connector は、Office 365 Enterprise E5 が利用可能なすべての国で利用できます。

このトピックは、以下のセクションで構成されています。

- [Cloud Connector Edition コンポーネント](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Cloud Connector エディションのトポロジ](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [展開の要件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [展開の前に収集する必要がある情報](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [ダイヤルプランに関する考慮事項](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性に関する考慮事項](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Cloud Connector のメディアフロー](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [監視とトラブルシューティング](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [詳細情報](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition コンポーネント
<a name="BKMK_Components"> </a>

Cloud Connector エディションでは、エッジコンポーネント、仲介コンポーネント、中央管理ストア (CMS) の役割で構成される最小限の Skype for Business Server トポロジを含むパッケージ化された Vm のセットを展開します。 また、Cloud Connector の内部機能に必要なドメインコントローラーもインストールします。 これらのサービスは、Skype for Business Online サービスを含む Microsoft 365 または Office 365 組織とのハイブリッド用に構成されています。

![Cloud Connector Edition コンポーネント](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Cloud Connector コンポーネントは、次の機能を提供します。

- **エッジコンポーネント**-オンプレミストポロジとオンラインサービスとの間の通信はエッジコンポーネントを通過します。これには、次のコンポーネントが含まれます。

  - **アクセスエッジ**-オンプレミス展開と Skype For business Online との間に SIP ルーティングを提供します。

  - **メディアリレー** -仲介コンポーネントと他のメディアエンドポイントとの間のメディアのルーティングを提供します。

  - **メディアリレー認証/MRAS** -メディアリレーへのアクセスのためのトークンを生成します。

- **送信ルーティング**-Cloud Connector アプライアンスに接続されているゲートウェイまたは SBCs 間の音声トラフィックの負荷分散を提供します。 呼び出しは、Cloud Connector アプライアンスに接続されているすべてのゲートウェイまたは SBCs 間で均等に分割されます。

    ポリシーに基づいたゲートウェイへのルーティングを提供します。 宛先 (発信) PSTN 番号に基づくグローバルポリシーのみがサポートされています。

- **中央管理ストア (cms) の役割**-Cms ファイル転送を含む、トポロジコンポーネントの構成ストアが含まれています。

- **中央管理ストア (cms) レプリカ**-cms 役割サーバー上のグローバル CMS DB から構成情報を同期します。

- **ドメインコントローラ**-Cloud Connector Active Directory ドメインサービスには、cloud connector コンポーネントの展開に必要なすべてのグローバル設定とグループが格納されています。 Cloud Connector アプライアンスごとに1つのフォレストが作成されます。 ドメインコントローラーは、運用 Active Directory との接続を持ってはなりません。 Active Directory サービスには次のものがあります。

  - Active Directory ドメイン サービス

  - 内部証明書を発行するための Active Directory 証明書サービス

- **仲介コンポーネント**-Skype for business ゲートウェイと PSTN ゲートウェイ間で SIP および Media ゲートウェイマッピングプロトコルを実装します。 グローバル CMS データベースから構成を同期する CMS レプリカが含まれています。

## <a name="cloud-connector-edition-topologies"></a>Cloud Connector エディションのトポロジ
<a name="BKMK_Topologies"> </a>

このディスカッションの目的で、PSTN サイトを参照します。 PSTN サイトは、クラウドコネクタアプライアンスを組み合わせたもので、同じ場所に展開され、共通の PSTN ゲートウェイが接続されています。 PSTN サイトでは、次のことを行うことができます。

- ユーザーに最も近いゲートウェイへの接続を提供します。

- 1つまたは複数の PSTN サイト内に複数の Cloud Connector アプライアンスを展開することによって、拡張性を確保します。

- 単一の PSTN サイト内に複数の Cloud Connector アプライアンスを展開することで、高可用性を実現します。

このトピックでは、PSTN サイトについて説明します。 PSTN サイトの計画の詳細については、「 [Plan For Cloud Connector EDITION PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md)」を参照してください。

次の Cloud Connector トポロジを展開できます。

- PSTN サイトごとに1つの Cloud Connector エディションのアプライアンス。 このトポロジは高可用性を提供しないため、評価のために推奨されます。

- 高可用性を実現するための PSTN サイトあたりの複数の Cloud Connector エディションのアプライアンス。

- 複数の Cloud Connector エディションのアプライアンスを備えた複数の PSTN サイト。高可用性の拡張性を提供します。 最大200サイトを展開できます。

トポロジを計画するときは、次の点を考慮してください。

- Cloud Connector 2.0 以降では、1つの PSTN サイトは最大16個の Cloud Connector アプライアンスを持つことができます。 以前のバージョンでは、サイトごとに最大4つのアプライアンスをサポートしています。

- Cloud Connector を使用してテストするハードウェア構成には、次の2種類があります。

  - 大規模なバージョンでは、大量の同時通話を処理することができ、すべての種類の運用環境でサポートされています。

  - 小規模なバージョンは、下位のハードウェア上で実行することを目的としており、評価の目的で、または通話量の少ないサイトで使用することができます。 小規模なバージョンの Cloud Connector を展開する場合は、運用クラスのハードウェア要件 (デュアル電源装置など) に注意する必要があります。

- Cloud Connector バージョン2.0 以降を所有しており、最大構成の16アプライアンス (より大きなハードウェア) を展開する場合、PSTN サイトは最大で8000の同時通話を処理できます。 小規模なバージョンを展開する場合、サポートされる制限は800です。

    また、一部のアプライアンスを高可用性のために専用にする必要もあります。 最低限の推奨事項は、高可用性のために1つのアプライアンスを予約する必要があることです。

  - バージョン2では、15 + 1 構成を展開する場合、PSTN サイトは最大7500の同時通話を処理できます。

  - 以前のバージョンを使用していて、最大 3 + 1 構成 (より大きなハードウェア) を展開する場合は、PSTN サイトで最大1500の同時通話を処理できます。 小規模なバージョンを展開する場合、サポートされる制限は150です。

-  PSTN サイトごとにさらに多くの通話を必要とする場合は、同じ場所に追加の PSTN サイトを展開することでスケールアップできます。

> [!NOTE]
> 記載されていない限り、以下の図と例では、より大きなバージョンの Cloud Connector を使用することを前提としています。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>単一の PSTN サイト内の単一の Cloud Connector アプライアンス

次の図は、単一の PSTN サイト内の単一の Cloud Connector エディションのアプライアンスを示しています。 Cloud Connector は、セキュリティを確保するために、境界ネットワーク内の1つの物理ホストマシンにインストールされた4つの Vm で構成されることに注意してください。

![1つの PSTN サイトがある1つの Cloud Connector](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>単一の PSTN サイト内の複数の Cloud Connector アプライアンス

 スケーラビリティと高可用性を確保するために、次の図に示すように、単一の PSTN サイト内に複数の Cloud Connector エディションを含めることを選択できます。 以下の点を考慮してください。

- 通話は、1つのプール内のクラウドコネクタ間でランダムな順序で分散されます。

- 容量計画のためには、次の計算に基づいて、1つまたは複数の Cloud connector がオフラインになった場合の負荷の処理能力を考慮する必要があります。

  - **N + 1 ボックス。** Cloud Connector の大規模なバージョンでは、N + 1 ボックスは 500 \* n の同時呼び出しを99.8% の可用性でサポートします。

    Cloud Connector の小規模バージョンでは、N + 1 ボックスは 50 \* n 個の同時通話を99.8% の可用性でサポートしています。

  - **N + 2 ボックス** より大規模な Cloud Connector の場合、N + 2 ボックスは 500 n 件の \* 同時通話を99.9% の可用性でサポートします。

    Cloud Connector の小規模バージョンでは、N + 2 ボックスは 50 \* n 件の同時通話を99.9% の可用性でサポートしています。

![1つの PSTN サイト内の2つのクラウドコネクタ](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>サイトごとに1つまたは複数の Cloud connector がある複数の PSTN サイト

各サイトに1つ以上の Cloud Connector エディションを持つ複数の PSTN サイトを選択することもできます。 PSTN サイトが同時通話の制限に達した場合は、別の PSTN サイトを追加して負荷を処理できます。

また、複数の PSTN サイトを使用して、ユーザーに最も近いゲートウェイへの接続を提供することもできます。 たとえば、シアトルとアムステルダムに PSTN ゲートウェイがあるとします。 2つの PSTN サイト (シアトルに1つずつ、1つはアムステルダム) を展開し、ユーザーに最も近い PSTN サイトを使用するように割り当てることができます。 シアトルのユーザーは、シアトルの PSTN サイトとゲートウェイにルーティングされますが、アムステルダムのユーザーはアムステルダムの PSTN サイトとゲートウェイにルーティングされます。

![2つの PSTN サイト内の Cloud Connector エディション](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>展開の要件
<a name="BKMK_Requirements"> </a>

Cloud Connector エディションを展開する前に、ご使用の環境に次のものがあることを確認してください。

- **ホストマシンの場合-** Cloud Connector Vm は、Hyper-v の役割が有効になっている Windows Server 2012 R2 Datacenter edition (英語) を実行している専用ハードウェアに展開する必要があります。

    バージョン2.0 以降の場合、Skype for Business の社内ネットワーク接続スイッチにバインドされているホストコンピュータネットワークカードには、Cloud Connector 企業のネットワークコンピューターと同じサブネットに構成された IP アドレスが必要です。

- バージョン2.1 以降の場合、ホストアプライアンスには .NET Framework 4.6.1 以降がインストールされている必要があります。

- **仮想マシンの場合-** Windows Server 2012 R2 ISO (英語) イメージ (.iso)。 ISO は、Skype for Business Cloud Connector エディションを実行する仮想マシンの Vhd に変換されます。

- 展開内の各 Cloud Connector エディションに4つの Vm のインストールをサポートするために必要なハードウェア。 次の構成をお勧めします。

  - 64ビットデュアルプロセッサ、6コア (12 real コア)、2.50 ghz 以上

  - 64ギガバイト (GB) ECC RAM

  - 4 600 GB (またはそれ以上) 10K RPM 128 m キャッシュ SAS 6Gbps ディスク (RAID 5 構成で構成)

  - 3つの 1 Gbps RJ45 高スループットネットワークアダプター

- 最大50の同時通話をサポートする小規模バージョンの Cloud Connector エディションを展開する場合は、次のハードウェアが必要になります。

  - Intel i7 4790 クアッドコアコアとインテル4600グラフィックス (ハイエンドグラフィックスは不要)

  - 32 GB DDR3-1600 非 ECC

  - 2: RAID 0 で 1TB 7200RPM SATA III (6 Gbps)

  - 2: 1 Gbps イーサネット (RJ45)

- ホストマシンでインターネットを参照するためにプロキシサーバーが必要な場合は、次の構成変更を行う必要があります。

  - プロキシをバイパスするには、プロキシサーバーと、"192.168.213" を含むバイパスリストを使用して、WinHTTP プロキシ設定を設定します。 \*CloudConnector .ini ファイルで定義されているように、Cloud Connector Managements services と Skype for Business の社内のサブネットによって使用されるネットワーク。 そうしないと、管理接続が失敗し、Cloud Connector の展開と自動回復が妨げられます。 次に示すのは、サンプルの winhttp 構成コマンドです。 netsh winhttp set proxy "10.10.10.175: 8080" バイパス-list = " \* ... \* ;172.20. \* ; 192.168.218 \* \<ローカル \> "です。

  - ユーザー単位ではなく、コンピューターごとにプロキシ設定を指定します。 それ以外の場合、Cloud Connector のダウンロードは失敗します。 レジストリの変更またはグループポリシー設定を使用して、次のように、コンピューターごとにプロキシ設定を指定できます。

  - **レジストリ:** HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword: 00000000

  - **グループポリシー:** コンピューター \> 管理用テンプレート \> Windows コンポーネント \> Internet Explorer: ユーザーごとではなく、コンピューターごとにプロキシ設定を行います。

- 認定済みの PBX/トランクまたは認定済みの SBC/ゲートウェイ (少なくとも2つのゲートウェイが推奨)。

    Cloud Connector は、Skype for Business に認定されているものと同じセッションボーダーコントローラー (sbc) をサポートしています。 詳細については、「Skype for business[のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」を参照してください。

- ホストサーバーに Hyper-v をインストールして構成するためのアクセス許可を持つローカルサーバー管理者アカウント。 このアカウントは、Hyper-v がインストールおよび構成されているローカルサーバーに対する管理者アクセス許可を持っている必要があります。

- 展開時に、クラウドコネクタドメインでトポロジを作成して公開するためのアクセス許可を持つドメイン管理者アカウントを作成するように求められます。

- 外部 DNS レコード。このレコードは、インストールパッケージに含まれている CloudConnector .ini ファイルで定義されています。

  - エッジコンポーネントのアクセスエッジサービスの外部 DNS レコード。たとえば、[ap] のようになります。 \<ドメイン名 \> 。 PSTN サイトごとに1つのレコードが必要です。 このレコードには、そのサイトのすべてのエッジの IP アドレスが含まれている必要があります。

- 必要なすべての DNS および SRV レコードが作成された Microsoft 365 または Office 365 組織。

    > [!IMPORTANT]
    > テナントを Cloud Connector エディションと統合する場合、既定のドメインサフィックス onmicrosoft.com を組織の SIP ドメインとして使用することはサポートされていません。 > sip を使用できません。 \<\>この DNS レコードは Microsoft 365 および Office 365 によって使用されるため、クラウドコネクタエッジアクセスプロキシインターフェイスの名前としてドメイン名を指定します。

- パブリック証明機関 (CA) から取得された外部エッジの証明書。

- 必要なポートを通過するトラフィックを許可するファイアウォールルールが完了していること。

- ホストマシンと Vm のインターネット接続。 Cloud Connector は、いくつかのソフトウェアをインターネットからダウンロードします。そのため、Cloud Connector ホストマシンと Vm がインターネットに接続して必要なソフトウェアをダウンロードできるように、ゲートウェイと DNS サーバーの情報を提供する必要があります。

- ホストコンピューターにインストールされているテナントのリモート PowerShell モジュール。

- リモート PowerShell を実行するための Skype for Business 管理者の資格情報。

    > [!IMPORTANT]
    > 管理者アカウントでは、多要素認証を有効にしないでください。

> [!NOTE]
> Cloud Connector の展開は、Microsoft Hyper-v 仮想化プラットフォームでのみサポートされています。 VMware や Amazon Web サービスなどのその他のプラットフォームはサポートされていません。

> [!NOTE]
> Cloud Connector を実行するためのハードウェアの最小ガイダンスは、基本的なハードウェア容量 (コア、MHz、gb など) に基づいて、コンピューターのアーキテクチャに埋もれた無形パフォーマンスの障害に対応するためのバッファーを備えています。 Microsoft では、最小限のガイダンスを満たす市販の使用可能なハードウェアで、最悪のケース負荷テストを実行しています。 メディアの品質とシステムのパフォーマンスが確認されます。 公式 Cloud Connector アプライアンスパートナーには、個別にパフォーマンスをテストし、負荷と品質の要件を満たすためにハードウェアの適合性によって、それぞれの専用のクラウドコネクタハードウェア実装が用意されています。

> [!NOTE]
> AudioCodes および Sonus によって生成されたデバイスは、コードを変更し、Windows Server Standard edition のサーバー上で実行します。 これらのデバイスはサポートされています。

## <a name="information-you-need-to-gather-before-deployment"></a>展開の前に収集する必要がある情報
<a name="BKMK_PlanDeployment"> </a>

展開を開始する前に、展開の規模、サービス対象の SIP ドメイン、および展開を計画している各 PSTN サイトの構成情報を特定する必要があります。 最初に、次の操作を行います。

- 会社で使用している SIP Uri に基づいて、この展開で提供されるすべての SIP ドメインを特定します。

- 展開する必要がある PSTN サイトの数を決定します。

- Cloud Connector エディションごとにインストールする4つの Vm をサポートするために必要なハードウェアが用意されていることを確認します。

展開を計画している PSTN サイトごとに、次のことを行う必要があります。

- 各 Cloud Connector アプライアンス内のすべてのコンポーネントの名前を作成します (「[展開パラメーターの決定」を](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)参照してください)。

- ポート範囲を定義します (「 [Ports and プロトコル」を](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)参照してください)。

- エッジコンポーネントの外部 DNS レコードを作成します (「[展開の要件」を](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)参照してください)。

- エッジコンポーネントの証明書の要件を決定します (「[証明書の要件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)」を参照してください)。

### <a name="ports-and-protocols"></a>ポートとプロトコル
<a name="BKMB_Ports"> </a>

メディアポート範囲を定義するときは、次の点に注意してください。

- クライアントは、メディアトラフィックに対してポート範囲5万から50019を常に使用します。この範囲は Skype for Business Online で事前に定義されており、変更することはできません。

- 既定では、仲介コンポーネントは、メディアトラフィックにポート範囲 49 152 ~ 57 500 を使用します。 ただし、接続は内部ファイアウォールを介して確立されるので、セキュリティ上の理由から、トポロジ内でこのポート範囲を制限することができます。 通話ごとに最大4つのポートが必要です。 仲介コンポーネントと PSTN ゲートウェイ間のポート数を制限する場合は、ゲートウェイで対応するポート範囲も構成する必要があります。

- 境界ネットワークには、Cloud Connector を展開する必要があります。 これは、2つのファイアウォールがあることを意味します。

  - 最初のファイアウォールは、インターネットと境界ネットワークの間の外部にあります。

  - 2番目のファイアウォールは、境界ネットワークと内部ネットワークの間の内部にあります。

    クライアントは、インターネットまたは内部ネットワークに存在することができます。

  - インターネットのクライアントは、エッジコンポーネントを経由して、外部ファイアウォールを介して PSTN に接続します。

  - 内部ネットワークのクライアントは、内部ファイアウォールを介して境界ネットワークの仲介コンポーネントに接続します。これにより、トラフィックは SBC または PSTN ゲートウェイに接続されます。

    これは、両方のファイアウォールでポートを開く必要があることを意味します。

次の表は、外部および内部ファイアウォールのポートとポート範囲を示しています。

次の表は、内部ネットワークと仲介コンポーネントのクライアント間の通信を可能にするためのポートとポート範囲を示しています。

**内部ファイアウォール**



|**送信元 IP**|**送信先 IP アドレス**|**送信元ポート**|**宛先ポート**|
|:-----|:-----|:-----|:-----|
|Cloud Connector 仲介コンポーネント  <br/> |SBC/PSTN ゲートウェイ  <br/> |任意  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN ゲートウェイ  <br/> |Cloud Connector 仲介コンポーネント  <br/> |任意  <br/> |TCP 5068/TLS 5067  <br/> |
|Cloud Connector 仲介コンポーネント  <br/> |SBC/PSTN ゲートウェイ  <br/> |UDP 49 152-57 500  <br/> |内容\*\*\*  <br/> |
|SBC/PSTN ゲートウェイ  <br/> |Cloud Connector 仲介コンポーネント  <br/> |内容\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Cloud Connector 仲介コンポーネント  <br/> |内部クライアント  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-対して  <br/> オプション  <br/> |
|Cloud Connector 仲介コンポーネント  <br/> |内部クライアント  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-対して  <br/> |
|内部クライアント  <br/> |Cloud Connector 仲介コンポーネント  <br/> |TCP 50000-対して  <br/> |TCP 49 152-57 500\*  <br/> |
|内部クライアント  <br/> |Cloud Connector 仲介コンポーネント  <br/> |UDP 50000-対して  <br/> |UDP 49 152-57 500\*  <br/> |

\*これは、仲介コンポーネントの既定のポート範囲です。 最適な通話フローの場合は、1回の通話で4つのポートが必要です。

\*\*このポートは、SBC/PSTN ゲートウェイで構成する必要があります。5060は例です。 SBC/PSTN ゲートウェイでは、他のポートを構成できます。

\*\*\*SBC/ゲートウェイの製造元によって許可されている場合は、SBC/ゲートウェイのポート範囲を制限することもできますのでご注意ください。

セキュリティ上の理由から、仲介コンポーネントのポート範囲を制限するには、 [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps)コマンドレットを使用します。

たとえば、次のコマンドを実行すると、仲介コンポーネントがメディアトラフィックに対して使用するポートの数を、オーディオの場合は 50 000 ~ 51 000 に制限します (入力および出力)。 この構成では、仲介コンポーネントは250の同時呼び出しを処理できるようになります。 また、SBC/PSTN ゲートウェイのこの範囲を制限することも必要になることに注意してください。

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

仲介コンポーネントの名前を取得し、既定のポートを表示するには、次のように、 [Get-help service](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)コマンドレットを使用できます。

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

次の表に、Cloud Connector エッジコンポーネントと外部ファイアウォールの間の通信を有効にするためのポートとポート範囲を示します。 この表は、最低限の推奨事項を示しています。

この場合、インターネットへのすべてのメディアトラフィックは、次のようにオンラインエッジを介して流れます: ユーザーエンドポイント-- \> オンラインエッジ-- \> Cloud Connector エッジ:

**外部ファイアウォール-最小構成**



|**送信元 IP**|**送信先 IP アドレス**|**送信元ポート**|**宛先ポート**|
|:-----|:-----|:-----|:-----|
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |TCP (MTLS) 5061  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP (MTLS) 5061  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP 80  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |UDP 53  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP 53  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |

次の表に、Cloud Connector エッジコンポーネントと外部ファイアウォールの間の通信を有効にするためのポートとポート範囲を示します。 次の表に、推奨されるソリューションを示します。

この場合、インターネットのエンドポイントのすべてのメディアトラフィックは、直接 Cloud Connector エッジコンポーネントに流れることができます。 メディアパスは、ユーザーエンドポイント- \> Cloud Connector エッジになります。

> [!NOTE]
> このソリューションは、ユーザーのエンドポイントが対称 NAT の背後にある場合は機能しません。

**外部ファイアウォール-推奨構成**


|**送信元 IP**|**送信先 IP アドレス**|**送信元ポート**|**宛先ポート**|
|:-----|:-----|:-----|:-----|
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |TCP (MTLS) 5061  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP (MTLS) 5061  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP 80  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |UDP 53  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |任意  <br/> |TCP 53  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |TCP 50000-59999  <br/> |任意  <br/> |
|Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |UDP 3478。UDP 50000-59999  <br/> |任意  <br/> |
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |TCP 443。TCP 50000-59999  <br/> |
|任意  <br/> |Cloud Connector エッジ外部インターフェイス  <br/> |任意  <br/> |UDP 3478。UDP 5万-59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>ホストインターネット接続の要件
<a name="BKMB_Ports"> </a>

ホストコンピューターは、クラウドコネクタを正常にインストール、更新、および管理するために、外部リソースにアクセスできる必要があります。 次の表に、ホストコンピューターと外部リソース間で必要な接続先とポートを示します。

|Direction  <br/> |発信元 IP アドレス  <br/> |送信先 IP アドレス  <br/> |送信元ポート  <br/> |宛先ポート  <br/> |プロトコル  <br/> |用途  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|送信  <br/> |Cloud Connector ホスト Ip  <br/> |any  <br/> |any  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|送信  <br/> |Cloud Connector ホスト Ip  <br/> |any  <br/> |any  <br/> |80、443  <br/> |TCP  <br/> |証明書失効リスト (CRL)  <br/> |
|送信  <br/> |Cloud コネクタ r ホスト Ip  <br/> |any  <br/> |any  <br/> |80、443  <br/> |TCP  <br/> |Cloud Connector の更新プログラム  <br/> Skype for Business Online  <br/> 管理 PowerShell  <br/> Windows Update  <br/> |

その他の制限ルールが必要な場合は、次のホワイトリストにある Url を参照してください。

- Office の[証明書失効リストの url](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) [365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update:[ソフトウェア更新プログラム用にファイアウォールを構成する方法](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Online 管理者 PowerShell: \* . online.lync.com

    この宛先にプロキシ除外が必要な場合は、WinHTTP バイパス一覧に追加する必要があります。

- Cloud Connector の更新プログラム:[ダウンロードセンター](https://aka.ms/CloudConnectorInstaller)、 [https://go.microsoft.com](https://go.microsoft.com) 、および[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>エッジコンポーネントの DNS 名の解決
<a name="BKMB_Ports"> </a>

エッジコンポーネントは、Microsoft 365 または Office 365 サービスの外部名と他の Cloud Connector コンポーネントの内部名を解決する必要があります。

各エッジコンポーネントは、外部および内部接続インターフェイスを備えたマルチホームのコンピューターです。 Cloud Connector は、境界ネットワーク内のドメインコントローラーコンポーネントに DNS サーバーを展開します。 エッジサーバーは、すべての名前解決のために境界内の DNS サーバーをポイントできますが、クラウドコネクタ DNS サーバーが外部名を解決できるようにするには、1つ以上の DNS A レコードを含む DNS ゾーンを、他のパブリック DNS サーバーに名前参照を参照する外部クエリに設定する必要があります。

.Ini ファイルでは、SIP ドメインと同じドメイン空間にあるゲートウェイの FQDN 名を設定すると、この SIP ドメインの権限のある領域が境界内の DNS サーバーに作成されます。 エッジサーバーがこの DNS サーバーを指して名前を解決している場合、エッジは _sipfederationtls を解決しません。 \<yourdomain \> DNS レコード。通話フローに必要です。 この場合、Microsoft では、インターネット名参照を解決するためにエッジの外部インターフェイスに DNS サーバーを提供することをお勧めします。また、各エッジコンポーネントは、ホストファイルを使用して、他の Cloud Connector コンポーネント名を IP アドレスに解決する必要があります。

> [!NOTE]
> セキュリティ上の理由から、クラウドコネクタの DNS サーバーが名前解決のために実稼働ドメインの内部サーバーをポイントしないようにすることをお勧めします。

### <a name="determine-deployment-parameters"></a>展開パラメーターの決定
<a name="BKMK_SiteParams"> </a>

最初に、次の一般的な展開パラメーターを定義する必要があります。


|**Item**|**説明**|**メモ**|
|:-----|:-----|:-----|
|SIP ドメイン  <br/> |会社のユーザーが使用している SIP URI。 この展開で提供されるすべての SIP ドメインを指定します。 複数の SIP ドメインを持つことができます。  <br/> ||
|PSTN サイト数  <br/> |展開される PSTN サイトの数。  <br/> ||

展開を計画している PSTN サイトごとに、展開を開始する前に、次の情報を収集する必要があります。 この情報は、CloudConnector の .ini ファイルを更新するときに指定する必要があります。

ゲートウェイ情報を構成する場合は、次の点に注意してください。

- ゲートウェイが1つだけの場合は、2番目のゲートウェイの .ini ファイルのセクションを削除します。 3つ以上のゲートウェイがある場合は、既存の形式に従って新しいゲートウェイを追加します。

- ゲートウェイの IP アドレスとポートが正しいことを確認します。

- PSTN ゲートウェイレベルの HA をサポートするには、セカンダリゲートウェイを維持するか、ゲートウェイを追加します。

オプション発信呼び出し番号を制限するには、LocalRoute 値を更新します。



|**サイトのパラメーター**|**説明**|**メモ**|
|:-----|:-----|:-----|
|仮想マシンのドメイン名  <br/> |Cloud Connector の内部コンポーネントのドメイン名。 このドメインは、運用ドメインとは別のものである必要があります。 この名前は、すべての Cloud Connector アプライアンスで同じである必要があります。  <br/> .Ini ファイルでの名前: "VirtualMachineDomain"  <br/> |. ローカルドメインが優先されます。  <br/> |
|Cloud Connector ドメインコントローラー名  <br/> |ドメインコントローラーの名前。  <br/> .Ini ファイルでの名前: "ServerName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|Cloud Connector ドメインコントローラー IP/サブネットマスク  <br/> |ドメインコントローラーの IP アドレス。  <br/> .Ini ファイルでの名前: "IP"  <br/> ||
|Microsoft 365 または Office 365 Online サービス Fqdn  <br/> |世界中の Microsoft 365 または Office 365 インスタンスでは、ほとんどの場合、既定値である必要があります。  <br/> .Ini ファイルでの名前: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business サイト名。たとえば、シアトルというようになります。  <br/> .Ini ファイルでの名前: "SiteName"  <br/> リリース1.4.1 以降では、サイト名がサイトごとに異なる必要があります。また、名前は、存在する場合は、(Microsoft 365 または Office 365 で定義された) PSTN サイトと一致する必要があります。 サイト内の最初のアプライアンスを登録すると、PSTN サイトが自動的に作成されることに注意してください。  <br/> ||
|ハードウェアの種類  <br/> リリース1.4.1 以降  <br/> |ハードウェアの種類。 既定値は Normal です。 最小値に設定することもできます。  <br/> ||
|Country Code  <br/> |ダイヤルの国番号。  <br/> .Ini ファイルでの名前: "CountryCode"  <br/> ||
|都市  <br/> |City (省略可能)。  <br/> .Ini ファイルでの名前: "City"  <br/> ||
|State  <br/> |State (省略可能)。  <br/> .Ini ファイルでの名前: "State"  <br/> ||
|ベース VM IP アドレス  <br/> |すべての Cloud Connector 仮想マシンの VHDX の作成に使用される一時ベース VM の IP アドレス。 この IP は、次の手順で定義されているものと同じ境界の企業ネットワークサブネットに存在する必要があり、インターネットアクセスが必要です。 インターネットにルーティングできるように、企業の既定のゲートウェイと DNS を定義してください。  <br/> .Ini ファイルでの名前: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> リリース1.4.1 以降  <br/> |Windows Server Update Services (WSUS) のアドレス。 Microsoft Update からの更新プログラムをホストするイントラネットサーバー。  <br/> WSUS を必要としない場合は、空白のままにしておくことができます。  <br/> ||
|内部ネットワークのサブネットマスク  <br/> |Cloud Connector は、Cloud Connector コンポーネント間の内部通信用に IP ネットワークを構成します。 エッジは、インターネット接続を可能にする別のサブネットにも接続されている必要があります。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "CorpnetIPPrefixLength"  <br/> ||
|外部ネットワークのサブネットマスク  <br/> |エッジコンポーネントの外部ネットワーク用。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "Interneヒントプレフィックス"  <br/> ||
|内部ネットワークのスイッチ名  <br/> |内部クラウドコネクタネットワークに使用されるスイッチの名前。  <br/> ほとんどの場合、既定の推奨値を使用できます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "CorpnetSwitchName"  <br/> ||
|外部ネットワークのスイッチ名  <br/> |外部クラウドコネクタネットワークに使用されるスイッチの名前。  <br/> ほとんどの場合、既定の推奨値を使用できます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "InternetSwitchName"  <br/> ||
|内部ネットワークの既定のゲートウェイ  <br/> |このゲートウェイは、インターネットへのアクセスを提供する必要があります (インターネットにも DNS サーバーを設定する必要があります)。また、Cloud Connector コンポーネントの内部インターフェイス上で構成されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "CorpnetDefaultGateway"  <br/> ||
|エッジコンポーネントの外部インターフェイスの既定のゲートウェイ  <br/> |エッジコンポーネントの外部インターフェイスで構成されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "InternetDefaultGateway"  <br/> ||
|内部ネットワークの DNS サーバー  <br/> |一時 VM の内部インターフェイス上で構成されます。 インターネット名の名前解決を提供する必要があります。 DNS サーバーを提供しないと、インターネット接続が失敗し、展開が完了しません。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "CorpnetDNSIPAddress"  <br/> ||
|エッジコンポーネントの外部インターフェイスの DNS サーバー  <br/> |エッジの外部インターフェイス上で構成されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "InternetDNSIPAddress"  <br/> ||
|管理スイッチ名  <br/> |管理スイッチは、自動的に作成される一時的なスイッチで、展開中に Cloud Connector の構成に使用されます。 展開後は自動的に切断されます。 Cloud Connector で使用されている他のすべてのネットワークとは別のサブネットである必要があります。  <br/> ほとんどの場合、既定の推奨値を使用できます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "ManagementSwitchName"  <br/> ||
|管理サブネットアドレス/サブネットマスク  <br/> |管理サブネットは、自動的に作成される一時的なサブネットで、展開中に Cloud Connector の構成に使用されます。 展開後に自動的に削除されます。 Cloud Connector で使用されている他のすべてのネットワークとは別のサブネットである必要があります。  <br/> .Ini ファイルでの名前: "Parameters for a pool of VM network" の "ManagementIPPrefix" および "Managementipprefix"  <br/> ||
|中央管理ストア (CMS) マシン  <br/> |中央管理ストア (CMS) に使用される単一の FQDN。 AD ドメイン名は、FQDN の生成に使用されます。  <br/> .Ini ファイルでの名前: "Parameters for Primary Central Management Service" の "ServerName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> (CMS プール名 = サーバー名)  <br/> |
|CMS コンピューターの IP アドレス  <br/> |CMS サーバーの IP アドレス (境界ネットワークの内部)。  <br/> INI ファイルでの名前: "Parameters for Primary Central Management Service" の "IP"  <br/> ||
|ファイル共有名  <br/> |CmsFileStore など、Skype for Business レプリケーションデータ用の CMS サーバー上に作成するファイル共有名 (たとえば、)。  <br/> ほとんどの場合、既定の推奨値を使用できます。  <br/> .Ini ファイルでの名前: "Parameters for Primary Central Management Service" の "CmsFileStore"  <br/> ||
|仲介コンポーネントのプール名  <br/> |仲介コンポーネントのプール名。 Netbios 名のみを入力します。 AD ドメイン名は、FQDN の生成に使用されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of 仲介 Servers" の "PoolName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|仲介コンポーネント名  <br/> |仲介コンポーネント1のコンポーネント名。 Netbios 名のみを入力します。 AD ドメイン名は、FQDN の生成に使用されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of 仲介 Servers" の "ServerName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|仲介コンポーネントのコンピューターの IP アドレス  <br/> |仲介コンポーネントの内部企業の IP (境界ネットワーク内の内部)。  <br/> .Ini ファイルでの名前: "Parameters for a pool of 仲介 Servers" の "IP"  <br/> ||
|エッジプールの内部名  <br/> |エッジコンポーネントのプール名。 Netbios 名のみを入力します。 AD ドメイン名は、FQDN の生成に使用されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "InternalPoolName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|エッジサーバーの内部名  <br/> |エッジコンポーネントのコンポーネント名。 Netbios 名のみを入力します。 AD ドメイン名は、FQDN の生成に使用されます。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "InternalServerName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|エッジサーバーの内部 IP  <br/> |Cloud Connector の他のコンポーネントと通信するエッジコンポーネントの内部境界ネットワークの IP。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "Internal、Erips"  <br/> ||
|アクセスプールの外部名  <br/> |アクセスエッジの名前。たとえば、[AP] のようになります。 この名前は、SSL 証明書に指定された名前と一致している必要があります。 Netbios 名のみを入力します。 SIP ドメイン名は、FQDN の生成に使用されます。 プール内のすべてのエッジコンポーネントに対して、1つの外部プール名が使用されます。 PSTN サイトごとに1つのエッジアクセスプールが必要です。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "ExternalSIPPoolName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> "sip" は予約されているため、名前として使用することはできません。  <br/> 生成された FQDN 名は、SSL 証明書に指定された名前と一致する必要があります。  <br/> |
|アクセスエッジの外部 IP  <br/> |エッジコンポーネントの外部 IP-NAT が利用できない場合はパブリック IP、または変換された IP (マッピングされている場合は両方のアドレスを指定してください)。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "ExternalSIPIPs"  <br/> ||
|メディアリレー名  <br/> |オーディオビデオメディアリレーエッジの名前。たとえば、「MR」とします。 1つの外部プール名がプール内のすべてのエッジコンポーネントに対して使用されます。 PSTN サイトごとに1つのエッジメディアリレープールが必要です。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "ExternalMRFQDNPoolName"  <br/> |15文字以下にする必要があります。 Netbios 名のみを入力します。  <br/> |
|メディアリレーエッジの外部 IP  <br/> |現時点では1つの IP のみがサポートされているため、これはアクセスエッジと同じ IP になります (マッピングされている場合は、両方のアドレスを指定してください)。 アクセスエッジのエッジコンポーネントの外部 IP と同じアドレスにすることができます。 注エッジが NAT の背後にある場合は、次のパラメーターの値も指定する必要があります。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "ExternalMRIPs"  <br/> ||
|メディアリレーエッジの外部 IP (エッジが NAT の背後にある場合)  <br/> |エッジが NAT の背後にある場合は、NAT デバイスのパブリックアドレスも指定する必要があります。  <br/> .Ini ファイルでの名前: "Parameters for a pool of Edge Servers" の "ExternalMRPublicIPs"  <br/> ||
|音声ゲートウェイ1の製造元とモデル  <br/> |SBC/Voice gateway の製造元とモデルを指定します。 デバイスまたは SIP トランクは、テスト済みのデバイスのリストから接続できることに注意 [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) してください。  <br/> ||
|音声ゲートウェイ2の製造元とモデル (3 つ以上のゲートウェイがある場合はこの行をコピーしてください)  <br/> |音声ゲートウェイの製造元とモデルを指定します。 でデバイスをテストしたデバイスのリストから接続できることに注意 [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) してください。  <br/> ||
|音声ゲートウェイ1の名前  <br/> |AD ドメインを使用してコンピューターの FQDN を生成するために使用されます。 仲介コンポーネントと音声ゲートウェイ間で TLS を使用する場合に必要です。 FQDN の使用を計画しない場合、たとえば、TLS が必要ない、または音声ゲートウェイが FQDN (IP のみ) を使用した接続をサポートしていない場合は、を指定してください。  <br/> ||
|音声ゲートウェイ2の名前 (3 つ以上のゲートウェイがある場合はこの行をコピーしてください)  <br/> |AD ドメインを使用してコンピューターの FQDN を生成するために使用されます。 仲介コンポーネントと音声ゲートウェイ間で TLS を使用する場合に必要です。 FQDN の使用を計画しない場合、たとえば、TLS が必要ない、または音声ゲートウェイが FQDN (IP のみ) を使用した接続をサポートしていない場合は、を指定してください。  <br/> ||
|音声ゲートウェイ1の IP アドレス  <br/> |音声ゲートウェイの IP アドレス。  <br/> ||
|音声ゲートウェイ2の IP アドレス (3 つ以上のゲートウェイがある場合はこの行をコピーしてください)  <br/> |音声ゲートウェイの IP アドレス。  <br/> ||
|音声ゲートウェイ1のポート番号 (3 つ以上のゲートウェイがある場合はこの行をコピーしてください)  <br/> |音声ゲートウェイの SIP トランクがリッスンするポート (5060 など)。  <br/> ||
|音声ゲートウェイ2のポート#  <br/> |音声ゲートウェイの SIP トランクがリッスンするポート (5060 など)。  <br/> ||
|SIP トラフィックの音声ゲートウェイ1のプロトコル  <br/> |TCP または TLS。  <br/> ||
|SIP トラフィックの音声ゲートウェイ2プロトコル (3 つ以上のゲートウェイがある場合はこの行をコピーしてください)  <br/> |TCP または TLS。  <br/> ||
|エッジコンポーネントとの間のトラフィックの外部メディアポート範囲  <br/> |エッジの外部インターフェイスとの間で送受信されるメディアトラフィックの TCP/UDP ポート範囲。 常に 50 000 から開始する必要があります。 詳細については、「ポートとプロトコル」を参照してください。  <br/> |5万 ~ 59 999  <br/> |
|内部ファイアウォールを介して仲介コンポーネントと通信するためのメディアポートの範囲  <br/> |仲介コンポーネントがクライアントとゲートウェイとの通信に使用する UDP ポート範囲 (通話ごとに推奨4ポート)。  <br/> ||
|内部ファイアウォール経由で Skype for Business クライアントと通信するためのメディアポートの範囲  <br/> |計画のために変更することはできません。 内部ネットワーク内の Skype for Business クライアントと仲介コンポーネントの間で通信を行うには、内部ファイアウォールでポートを開く必要があります。  <br/> |50 000 ~ 50 019  <br/> |
|パブリック証明書のパスワード  <br/> |スクリプトで指定する必要があります。  <br/> ||
|セーフモードの管理者パスワード  <br/> バージョン1.4.2 のみ  <br/> |内部 CC ドメインのセーフモードの管理者パスワード。  <br/> ||
|Cloud Connector ドメイン管理者パスワード  <br/> バージョン1.4.2 のみ  <br/> |Cloud Connector ドメイン管理者のパスワード (運用ドメインとは異なります)。 ユーザー名は管理者です。 ユーザー名を変更することはできません。  <br/> ||
|仮想マシンの管理者パスワード  <br/> バージョン1.4.2 のみ  <br/> |展開中に管理ネットワークを構成するために使用します。  <br/> ユーザー名は管理者です。 ユーザー名を変更することはできません。  <br/> ||
|CABackupFile  <br/> バージョン2.0 以降  <br/> |Cloud Connector サイトに複数のアプライアンスを展開するときに、Active Directory サーバーからファイルに証明機関サービスを保存するために使用します。 CA バックアップファイルを新しい追加アプライアンスに正常にインポートするために、1つの Cloud Connector サイト内のすべてのアプライアンスで同じパスワードを使用してください。  <br/> ||
|CCEService  <br/> バージョン2.0 以降  <br/> |Cloud Connector Management service で使用されます。Cloud Connector サイトディレクトリへのアクセスが必要です。 1つの Cloud Connector サイト内のすべてのアプライアンスで同じパスワードを使用してください。  <br/> ||
|Microsoft 365 または Office 365 テナント管理者  <br/> | このアカウントは cloud Connector によって使用され、Cloud Connector のテナント設定を更新して管理します。 <br/>  バージョン2.0 以降: Skype for Business の管理者権限を持つ専用の Microsoft 365 または Office 365 アカウントの資格情報。 <br/>  2.0 以前のバージョン: グローバルテナント管理者権限を持つ専用の Microsoft 365 または Office 365 アカウントの資格情報。 <br/> ||
|参照サポートを有効にする  <br/> |これにより、IP/PBX へのトランク構成で SIP 参照サポートが有効か無効かが定義されます。 既定値は True です。 IP/PBX ゲートウェイが参照サポートをサポートしている場合は、True のままにしてください。 そうでない場合は、この値を False に変更する必要があります。 ゲートウェイが参照をサポートしているかどうかがわからない場合は、「認定された[IP-pbx とゲートウェイ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」を参照してください。   <br/> ||
|EnableFastFailoverTimer  <br/> バージョン2.0 以降  <br/> |既定値の "True" の場合、送信呼び出しが10秒以内にゲートウェイによって応答されないと、次に使用可能なゲートウェイにルーティングされます。追加のトランクがない場合は、呼び出しは自動的に削除されます。  <br/> ただし、ネットワークとゲートウェイの応答が遅い組織や、呼び出しを確立するプロセスに10秒以上かかる場合は、呼び出しが不必要に削除される可能性があります。  <br/> UAE またはアフガニスタンなどの一部の国に電話をかける場合、通話の確立プロセスに10秒以上かかることがあります。 同様の問題が発生した場合は、値を False に変更する必要があります。 接続された SBC またはゲートウェイの対応する設定を忘れずに変更してください。  <br/> この値は、True または False にすることができます。 既定値は True です。  <br/> ||
|ForwardCallHistory  <br/> バージョン2.0 以降  <br/> | このパラメーターは、初回呼び出しの報告に使用される SIP ヘッダーを同時呼び出し、着信転送、および通話転送シナリオで有効にするために使用されます。 パラメーターを True に設定すると、2つの SIP ヘッダーが有効になります。 <br/>  履歴-情報 <br/>  参照元 <br/>  History-Info ヘッダーは、SIP 要求を再ターゲットするためのものです。また、要求履歴情報をキャプチャするための標準的なメカニズムを使用して、ネットワークやエンドユーザーにさまざまなサービスを提供することができます ([RFC 4244-セクション 1.1](http://www.ietf.org/rfc/rfc4244.txt))。 Cloud Connector トランクインターフェイスの場合、これは切り替わりおよび着信転送シナリオで使用されます。  <br/>  この値は、True または False にすることができます。 既定値は False です。 <br/> ||
|転送パラレル  <br/> バージョン2.0 以降  <br/> |PAI は、sip サーバーが認証されたユーザーの id をアサートできるようにする、SIP のプライベート拡張機能です。 SIP トランクプロバイダーでは、履歴情報と参照元ヘッダーが存在しない場合に、PAI を使用して、請求書を目的として使用することができます。 構成で P が有効になっている Id を転送すると、仲介サーバーは、SIP Tel URI を含む PAI ヘッダーを &amp; Cloud Connector から Sip トランクに転送します。 仲介サーバーは、 &amp; SIP トランクでクラウドコネクタに対して受信した TEL URI の e.164 番号を使用して PAI ヘッダーを転送します。 また、仲介サーバーは、いずれかの方向で受信したすべてのプライバシーヘッダーを転送します。 仲介サーバーによって送信された SIP 要求に、PAI ヘッダーと共に "Privacy: id" という形式のプライバシーヘッダーが含まれている場合、アサートされた id は、ネットワーク信頼ドメイン外のプライベートに保持する必要があります。  <br/> この値は、True または False にすることができます。 既定値は False です。  <br/> ||

### <a name="certificate-requirements"></a>証明書の要件
<a name="BKMK_Certs"> </a>

各エッジコンポーネントには、パブリック証明機関からの証明書が必要です。 エッジコンポーネント間でコピーするには、証明書がエクスポート可能な秘密キーを持っている必要があります。 証明書の要件を満たすには、次のオプションのいずれかを決定し、証明書のサブジェクト名 (SN) およびサブジェクトの別名 (SAN) を指定する必要があります。

 **単一の SIP ドメインがある場合:**

- **オプション1。** サブジェクト名には、エッジコンポーネントに割り当てたプール名を含める必要があります。 この名前は、オンラインの Skype for Business エッジコンポーネント用に予約されているため、サブジェクト名を sip.sipdomain.com できないことに注意してください。 SAN には、sip.sipdomain.com とアクセスエッジプールの名前が含まれている必要があります。

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **オプション2。** 展開するすべてのエッジプールサーバーで1つのワイルドカード証明書を使用する場合は、 \* 証明書のエッジプール名の代わりに、sipdomain.com のワイルドカード SAN エントリを使用できます。 サブジェクト名は、展開した任意のエッジプールのアクセスエッジプール名にすることができます。

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Sip の外部 DNS エントリを作成することはできません。 \<\>この名前は、Microsoft 365 または Office 365 の展開に属しているため、microsoft.rtc.management.xds.sipdomain。

> [!NOTE]
> 組織内に展開されているすべてのエッジプールに対して単一の証明書を使用し、オプション2で定義されたワイルドカード証明書を使用できない場合は、証明書の SAN 名に展開されているすべてのエッジプールの FQDN を含める必要があります。

 **複数の SIP ドメインがある場合:**

すべての SIP ドメインに対して sip.sipdomain.com を追加する必要があります。また、ドメインごとにアクセスエッジプールの名前を指定することもできます (これは、1つの物理プールで、名前が異なる場合があります)。 複数の sip ドメインシナリオでの SN と SAN のエントリの例を次に示します。

- **オプション1。** サブジェクト名には、エッジコンポーネントに割り当てたプール名を含める必要があります。 この名前は、オンラインの Skype for Business エッジコンポーネント用に予約されているため、サブジェクト名を sip.sipdomain.com できないことに注意してください。 SAN には、sip.sipdomain.com とアクセスエッジプールの名前が含まれている必要があります。

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>オプション2。</strong>展開するすべてのエッジプールサーバーで1つのワイルドカード証明書を使用する場合は、 \* 証明書のエッジプール名の代わりに、sipdomain.com のワイルドカード SAN エントリを使用できます。 サブジェクト名は、展開した任意のエッジプールのアクセスエッジプール名にすることができます。

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Sip の外部 DNS エントリを作成することはできません。 \<\>この名前は、Microsoft 365 または Office 365 の展開に属しているため、microsoft.rtc.management.xds.sipdomain。

展開の目的に応じて、次の表を使用できます。

|**オプション**|**説明**|**メモ**|
|:-----|:-----|:-----|
|展開では、どのオプションを使用しますか。  <br/> |オプション1または2  <br/> ||
|SN  <br/> |証明書に SN を指定する  <br/> ||
|サンノゼ  <br/> |証明書の SAN を提供します。  <br/> ||

ゲートウェイと仲介サーバーの間で TLS を使用している場合は、ゲートウェイに割り当てられている証明書のルート証明書 (完全な証明書チェーン) を取得する必要があります。

## <a name="dial-plan-considerations"></a>ダイヤルプランに関する考慮事項
<a name="BKMK_DailPlan"> </a>

Cloud Connector では、オンラインのダイヤルプランを使用する必要があります。 オンラインのダイヤルプランを構成する方法の詳細については、「[ダイヤルプラン](/microsoftteams/what-are-dial-plans)について」を参照してください。 
  
## <a name="high-availability-considerations"></a>高可用性に関する考慮事項
<a name="BKMK_HA"> </a>

Cloud Connector エディションを高可用性のために展開する場合は、互いのバックアップとして機能する、少なくとも2つのアプライアンスを展開します。 各アプライアンスは、エッジ、仲介、中央管理ストア (CMS)、ドメインコントローラーという4つのコンポーネントで構成されます。

一般に、アプライアンス内の1つのコンポーネントがダウンした場合、Cloud Connector エディションは引き続き通話を処理できますが、次の点を考慮する必要があります。

- **仲介、CMS、ドメインコントローラーの各コンポーネントに関する考慮事項**

    1つのアプライアンスの CMS またはドメインコントローラーコンポーネントが停止したと仮定します。 アプライアンスは引き続き着信および発信通話を処理できますが、ドメインコントローラーまたは CMS コンポーネントに到達できないときに仲介コンポーネントを再起動しても、仲介は機能しません。 同じことは、ドメインコントローラーがダウンしているときに CMS コンポーネントを再起動することにも当てはまります。

    **推奨事項:** コンポーネントを再起動する前に、アプライアンス内の他のコンポーネントの可用性を確認してください。

- **エッジコンポーネントに関する考慮事項**

    1つのアプライアンスのエッジコンポーネントが使用できない場合は、着信および発信通話の動作は次のように異なります。

  - **発信通話**-インターネットのユーザーから PSTN ネットワークへの通話。

    クラウド内の通話の配布メカニズムは、1つのエッジコンポーネントがダウンしていることを識別し、他のアプライアンスへのすべての通話をルーティングするので、発信呼び出しは成功します。

  - **着信通話**-PSTN ネットワークからローカルネットワークまたはインターネットにあるユーザーへの通話です。

     通話を受信したアプライアンスのエッジコンポーネントが動作していない場合、仲介コンポーネントが他のアプライアンスのエッジコンポーネントへの通話をリダイレクトできないため、このアプライアンスへの着信通話は成功しません。

    **推奨事項:** 監視システムが設置されている。 エッジコンポーネントの誤動作を特定したら、エッジコンポーネントが使用できないアプライアンス内のすべてのコンポーネントをシャットダウンします。

## <a name="cloud-connector-media-flow"></a>Cloud Connector のメディアフロー
<a name="BKMK_MediaFlow"> </a>

次の図は、Cloud Connector エディションを使用した発信および着信通話のフローの概要を示しています。 この情報は、接続が確立される方法を理解するのに役立ちます。

最初の図では、内部ユーザーが発信通話を次のように配置します。

1. Dave は、オンラインに所属しているユーザーが内部ネットワークに接続し、外部 PSTN ユーザーに電話を掛けます。

2. SIP トラフィックは、Skype for Business Online にルーティングされます。

3. Skype for Business Online は、番号の逆引き番号参照を実行します。 この番号は Skype for Business 組織のユーザーに属していないため、番号の逆引き参照が失敗します。

4. 通話は、エッジコンポーネント (最初にオンラインエッジ経由で SIP およびメディアフロー) にルーティングされます。メディアは、内部ファイアウォールを介して仲介コンポーネントに送られます。

5. ルートが存在する場合、エッジコンポーネントは境界ネットワークの仲介コンポーネントにトラフィックを中継します。

6. 仲介コンポーネントは、トラフィックを PSTN ゲートウェイに送信します。

![Cloud Connector の送信メディアフロー](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

次の図では、内部ユーザーが次のように着信呼び出しを受信します。

1. PSTN ゲートウェイは、オンラインに所属しているが、現在は内部ネットワークに属しているユーザー Dave に対して通話を受信します。

2. SIP トラフィックは、仲介コンポーネントにルーティングされます。

3. 仲介コンポーネントは、SIP トラフィックをエッジコンポーネントに送信し、Skype for Business Online に送られます。

4. Skype for Business Online は番号の逆引き番号参照を実行し、これがユーザー Dave であることを検出します。

5. SIP シグナリングは、すべての Dave に存在するすべてのポイントに送られます。

6. メディアトラフィックは、ゲートウェイと仲介コンポーネントの間、および仲介コンポーネントとエンドポイントの間で確立されます。

![Cloud Connector の受信メディアフロー](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>監視とトラブルシューティング
<a name="BKMK_Monitor"> </a>

監視とトラブルシューティングメカニズムは、すべての Cloud Connector アプライアンスに自動的にインストールされます。 このメカニズムでは、次のイベントが検出されます。

- Cloud Connector アプライアンスの1つまたは複数の仮想マシンが、内部またはインターネット仮想スイッチに接続されていません。

- Cloud Connector アプライアンスの1つまたは複数の仮想マシンが、保存済みまたは停止状態になっています。

- 実行されていないサービス。

  次のいずれかのイベントが検出された場合は、クラウドコネクタアプライアンス全体がドレインされ、オフラインとしてマークされ、誤動作しているアプライアンスへの通話を確立しないようにします。 Cloud Connector の自動回復機能は、サービスを復元し、アプライアンスをオンラインとしてマークします。 何らかの理由で自動回復に失敗した場合は、「 [Cloud Connector の展開のトラブルシューティング](troubleshoot-your-cloud-connector-deployment.md)」を参照してください。

  - 中央管理ストアの仮想マシン:

     - Skype for Business Master Replicator エージェント

     - Skype for Business Replica Replicator エージェント

  - 仲介サーバーの仮想マシンで、次のようにします。

     - Skype for Business Replica Replicator エージェント

     - Skype for Business Server の仲介

  - エッジサーバーの仮想マシン

     - Skype for Business Replica Replicator エージェント

     -  Skype for Business Server のアクセスエッジ

     - Skype for Business Server の音声ビデオエッジ

     - Skype for Business Server の音声/ビデオ認証

     - Skype for Business Server Web 会議エッジ

- エッジ上の "CS RTCSRV" に対する Windows ファイアウォールの受信規則。仲介サーバー上の "CS RTCMEDSRV" は無効になっています。

Cloud Connector 2.1 以降では、Operations Management Suite (OMS) を使用したクラウドコネクタの監視をサポートしています。 詳細については、「 [Operations Management Suite を使用してクラウドコネクタを監視する (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) 」を参照してください。

## <a name="for-more-information"></a>関連情報
<a name="BKMK_MoreInfo"> </a>

詳細については、次のトピックを参照してください。

- [Microsoft テレフォニー ソリューション](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Skype for Business Cloud Connector エディションを構成および管理する](configure-skype-for-business-cloud-connector-edition.md)

- [Cloud Connector エディションでのメディア バイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Cloud Connector エディションでのメディアバイパスの展開](deploy-media-bypass-in-cloud-connector.md)


