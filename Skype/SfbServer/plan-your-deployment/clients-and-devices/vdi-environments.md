---
title: VDI 環境での Skype for Business の計画
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための計画上の考慮事項について説明します。
ms.openlocfilehash: ca466b490fc04f44f2b8402c2f05aa1560e79774
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112793"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 環境での Skype for Business の計画
 
このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための計画上の考慮事項について説明します。 
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、セキュリティとコンプライアンスの問題が特に重要である一部の組織で使用されています。 ユーザーは、リモート デスクトップ サービスまたは同様のリモート接続を使用して、すべてのデスクトップ アプリケーションとファイルを使用して仮想デスクトップ上で作業を行います。 Skype for Business を完全なオーディオとビデオで使用するには、仮想デスクトップをホームとするクライアントで大量のオーディオとビデオの処理が必要になります。 追加の VDI プラグイン ソフトウェアを使用して、その処理をエンド ユーザーのローカル コンピューターにオフロードし、仮想デスクトップの負荷を軽減できます。
  
VDI プラグイン コンポーネントには、Microsoft、Citrix、または VMWare が提供する 3 つのソリューションがあります。 新しい展開では、Citrix HDX RealTime Optimization Pack ソリューションまたは VMWare Horizon Virtualization Pack のいずれかを使用することをお勧めします。 元の Lync VDI プラグインは、ライフサイクルの残りの部分で引き続きサポートされています。
  
- **Lync VDI** プラグインは Lync 2013 用に開発され、仮想デスクトップで実行されている Lync 2013 または Skype for Business 2015 クライアントと互換性があります。 これは、ローカル コンピューターにインストールし、仮想デスクトップ上のクライアントでローカルオーディオおよびビデオ デバイスを使用できるスタンドアロン アプリケーションです。 このプラグインでは、Windows 7、Windows 8、または Windows Server 2008 オペレーティング システムを実行する必要があるローカル コンピューターまたはシン クライアントに Skype for Business クライアントをインストールする必要があります。 (これらのオペレーティング システムを使用し、Microsoft でサポートされるシン クライアント デバイスには、Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610、HP t5740e が含まれます。このプラグインは引き続きサポートされますが、今後の更新プログラムは計画されていません。 Citrix ベースの仮想環境では、Citrix RealTime 最適化パックをお勧めします。
    
- **Citrix RealTime 最適化** パックは、Lync VDI プラグイン上に構築され、仮想デスクトップ上の Lync 2013 または Skype for Business 2016 クライアントと動作します。 これは、Citrix と Microsoft によって共同開発され、元の VDI プラグインを改善しました。 Windows および Windows 以外のオペレーティング システム (Windows 10、Mac、Linux を含む) を使用してクライアントにインストールできます。 このコンポーネントは、RealTime Connector (仮想デスクトップにインストールされている) と RealTime Media Engine (エンド ユーザーのローカル コンピューターにインストールされている) の 2 つのコンポーネントで構成されます。 これら 2 つのコンポーネントを使用すると、ユーザーのローカル コンピューターは、仮想デスクトップ上で実行されている Skype for Business クライアントを使用し、A/V 処理をローカル コンピューターに移動できます。 Citrix ベースの仮想デスクトップ環境では、Citrix RealTime 最適化パックが推奨され、さらにサポートが計画されています。
    
- VMWare と共同で開発された Skype for Business 用 VMWare Horizon **Virtualization** Pack を使用すると、優れたユーザー エクスペリエンスを提供しながら、仮想デスクトップで Skype for Business を配信できます。 このソリューションは、クライアントのメディア エンジンを活用して最適化されたソリューションを作成し、クライアント エンドポイントはオーディオ通話とビデオ通話のメディア オフロード機能を提供します。 このソリューションは、1 対 1 のコラボレーションのためにエンドポイント間で音声とビデオを直接配信したり、マルチパーティ会議や会議の中央マルチポイントコントロール ユニット (MCU) にオフロードすることができます。
    
> [!NOTE]
> Skype for Business Basic クライアントは、Citrix HDX RealTime Optimization Pack または VMWare Horizon Virtualization Pack ではサポートされていません。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime 最適化パック
<a name="Citrix_RT"> </a>

Citrix の VDI 環境プラグイン (XenApp と XenDesktop の機能) は、Lync 2013 および Skype for Business 2015 および 2016 (すべてのクリックでインストーラーを実行するフル クライアント、または 2017 年 1 月以降にリリースされた MSI インストーラー) クライアントと仮想デスクトップにインストールされます。 全体的な機能は Microsoft Lync VDI プラグインに基づいており、Windows 10、Macintosh、Linux など、さまざまなクライアント オペレーティング システムで動作します。
  
機能とサポートされるテクノロジの完全なリストは、Citrix Web サイトの [「Microsoft Skype for Business to XenApp および XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)への配信」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術的な概要](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business フィーチャー サポート](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon 仮想化パック
<a name="Citrix_RT"> </a>

VMWare の VDI 環境ソリューションは、仮想デスクトップにインストールされている Skype for Business 2015 および 2016 Full クライアントと互換性があります。 全体的な機能は Microsoft Lync VDI プラグインに基づいており、Windows 10、Macintosh、Linux など、さまざまなクライアント オペレーティング システムで動作します。 
  
機能とサポートされているテクノロジの詳細については、VMWare Web サイトの次のリンクを参照してください。
  
- [VMware Horizon 7.4 Horizon &amp; Client 4.7 の新機能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack for Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [VmWare Horizon を使用した Microsoft Skype for Business](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft の Lync VDI プラグイン
<a name="Citrix_RT"> </a>

Microsoft Lync VDI プラグイン ソリューションでは、ユーザーは Windows コンピューターまたはシン クライアント上に存在し、仮想デスクトップ上のクライアントからのオーディオ/ビデオ ストリームを処理するために Microsoft の Lync VDI プラグインをインストールする必要があります。 ユーザーは次の条件を実行します。
  
1. オーディオ/ビデオ デバイス (ヘッドセットやカメラなど) をローカル コンピューターに接続します。
    
2. Lync 2013 または Skype for Business 2015 クライアントを使用してリモート仮想デスクトップに接続します。
    
3. 仮想デスクトップで Skype for Business の資格情報を入力します。
    
4. ユーザー資格情報を再入力して、ローカル Windows コンピューターまたはシン クライアント上の Lync VDI プラグインとの接続を確立します。
    
接続が確立されると、ユーザーは音声通話とビデオ通話を行い、受信する準備が整います。 ローカル コンピューターがオーディオ/ビデオ処理を処理する場合、ネットワーク上のトラフィックと仮想デスクトップの負荷が最小限に抑えされます。
  
Microsoft の Lync VDI プラグインは、特定の Windows オペレーティング システムでのみサポートされ、Lync 2013 または Skype for Business 2015 クライアントのみをサポートします。 サポート [されるテクノロジと制限事項の詳細については](vdi-environments.md#Supported_virt) 、「サポートされる仮想化テクノロジと既知の制限」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- [サポートされている仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)
    
- [Lync VDI プラグインの前提条件](vdi-environments.md#VDI_prereq)
    
- [Skype for Business Server を使用して Lync VDI プラグインを展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix ナレッジ センターの [記事 CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI プラグインは [、Microsoft Lync VDI 2013 プラグイン (32 ビット)](https://www.microsoft.com/download/details.aspx?id=35457) または [Microsoft Lync VDI 2013 プラグイン (64 ビット) で利用できます](https://www.microsoft.com/download/details.aspx?id=35454)。 このプラグインは、名前にもかかわらず Skype for Business 2015 クライアントでサポートされています。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>サポートされている仮想化テクノロジと既知の制限
<a name="Supported_virt"> </a>

Lync VDI プラグインを使用すると、サポートされている仮想化テクノロジの音声通話とビデオ通話が可能です。 標準の電話規制に準拠して、E911 のサポートも含まれています。 以下のセクションでは、Lync VDI プラグインでサポートされる仮想化テクノロジと既知の機能の制限について説明します。
  
#### <a name="support-for-virtualization-technologies"></a>仮想化テクノロジのサポート

Lync VDI プラグインは、個人用仮想デスクトップ シナリオの完全なデスクトップ リモート セッションをサポートしますが、リモート デスクトップ セッションシナリオではサポートしません。 これらのシナリオは、次のように記述できます。
  
- **サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップ インフラストラクチャ (VDI)** このシナリオでは、各ユーザーはカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存できます。 Microsoft リモート デスクトップ サービスと VMware Horizon View は、Skype for Business 2015 で使用するためにテストされた実装の例です。 検証を行うその他の実装には、Citrix XenDesktop があります。 Microsoft によってテストされたベンダー固有の VDI 環境とクライアント ハードウェアの詳細については、「Microsoft Lync のインフラストラクチャ認定」 [を参照してください](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。
    
- **サポートされていません: リモート デスクトップ セッション。** このシナリオでは、各ユーザーはカスタマイズできない汎用仮想デスクトップ セッションにログオンします。 たとえば、Microsoft リモート デスクトップ セッション (RDSH) と Citrix XenApp と Citrix Receiver の組み合わせが含まれます。
    
Lync VDI プラグインは、アプリケーション仮想化などの他の仮想化テクノロジをサポートしていないので、アプリケーション全体をローカルにインストールする必要なくアプリケーションを使用できます。 実装例としては、Citrix XenApp と Microsoft Application Virtualization (App-V) が含まれます。 アプリケーション ストリーミング、アプリケーション リモート処理、および混合仮想化モード (フル デスクトップ リモート処理でのアプリケーション リモート処理など) はサポートされていません。
  
Lync VDI プラグインは、動的仮想チャネル (DVC) と呼ばれるプラットフォームに依存しない API を使用するように設計されています。 明示的にサポートされていないシナリオについては、VDI ソリューション プロバイダーのサポート ステートメントを参照してください。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI プラグインの前提条件
<a name="VDI_prereq"> </a>

VDI 環境では、仮想マシンとユーザーのローカル コンピューターは、このセクションで概説されている要件を満たす必要があります。
  
> [!NOTE]
>  仮想化ソリューション プロバイダーは、環境をインストールして展開する方法に関する詳細を提供できます。 Hyper-V およびリモート デスクトップ サービスに基づく仮想化環境の展開に関する一般的な情報については、「Microsoft ライブラリ: [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10))、リモート デスクトップ サービス」の記事を [参照Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
仮想マシンは、最新のサービス パックWindows 8 Windows 7、またはWindows Server 2008 R2を使用して構成する必要があります。
  
ユーザーのローカル コンピューターは、次の要件を満たしている必要があります。
  
- ユーザーは、Skype for Business Server または Lync Server 2013 に参加している必要があります。
    
- ローカル コンピューターで Windows Embedded Standard 7 と SP1、Windows 7 SP1、または windows 7 を実行している必要Windows 8。
    
- リモート デスクトップ サービスを使用している場合は、ローカル コンピューターのオペレーティング システムと一致する 32 ビットまたは 64 ビットの Lync VDI プラグインを選択します。 ローカル コンピューターと仮想マシンの両方に 32 ビットまたは 64 ビットのオペレーティング システムを使用する必要はありません。 別の仮想化ソリューションまたはプラットフォームを使用している場合は、プロバイダーの要件を参照してください。
    
- ローカル コンピューターは、リモート デスクトップ クライアント [の最新バージョンを実行している必要があります](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。 マイクロソフトからリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 
    
- ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート録音が無効となるように構成する必要があります。 Windows でリモート デスクトップ接続のこれらの設定を構成するには、次のセクション「リモート デスクトップ接続の設定を構成するには」を参照してください。 
    
Microsoft VDI プラグインは [、Microsoft Lync VDI 2013 プラグイン (32 ビット)](https://www.microsoft.com/download/details.aspx?id=35457) または [Microsoft Lync VDI 2013 プラグイン (64 ビット) で利用できます](https://www.microsoft.com/download/details.aspx?id=35454)。
  
#### <a name="known-feature-limitations"></a>既知の機能の制限
<a name="VDI_prereq"> </a>

VDI 環境で Skype for Business 2015 クライアントを使用する場合の既知の制限事項を次に示します。
  
通話委任および応答グループ エージェントの匿名化機能のサポートは限られています。
  
以下の機能はサポートされません。
  
- 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
- 複数表示のビデオ。
    
- 会話の録音
    
- 匿名で会議に参加する (つまり、組織とフェデレーションしない組織がホストする Skype for Business 会議に参加する)。
    
- Lync VDI プラグインを Lync Phone Edition デバイスと共に使用する。
    
- ネットワーク停止時の通話の継続
    
- カスタマイズされた着信音と保留音機能。
    
Lync VDI プラグインは、Microsoft 365 または 365 環境Officeサポートされていません。
  
> [!NOTE]
> Citrix RealTime 最適化パックは、Microsoft 365 および Office 365 をサポートします。 Citrix ベースの仮想環境については、サポートされている機能と[](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)バージョンの一覧について、Citrix の技術概要のドキュメントを参照してください。
  
## <a name="see-also"></a>関連項目
<a name="Citrix_RT"> </a>

[Skype for Business Server を使用して Lync VDI プラグインを展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)