---
title: VDI 環境における Skype for Business の計画
author: lanachin
ms.author: v-lanac
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
description: このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用する場合の計画に関する考慮事項について説明します。
ms.openlocfilehash: d2d65167eb574d17e31c19759364841147af6c05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803507"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 環境における Skype for Business の計画
 
このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用する場合の計画に関する考慮事項について説明します。 
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。 作業は、Remote Desktop Services または同様のリモート接続を使用して、すべてのデスクトップ アプリケーションとファイルを使用して、仮想デスクトップで行われます。 Skype for Business を使って、仮想デスクトップ上のクライアントでオーディオとビデオの処理が大量に必要になるような、接続上のオーディオとビデオをフルに使用します。 追加の VDI プラグインソフトウェアを使用すると、エンドユーザーのローカルコンピューターに処理の負荷を軽減し、仮想デスクトップの負荷を軽減することができます。
  
VDI プラグイン コンポーネントで使用できるソリューションには、マイクロソフト、Citrix、VMware が提供する 3 つのソリューションがあります。 新しい展開では、Citrix HDX リアルタイム最適化パックソリューションまたは VMWare ホライズン仮想化パックのいずれかを使用することをお勧めします。 元の Lync VDI プラグインは、そのライフサイクルの残りの部分で引き続きサポートされます。
  
- Lync **VDI プラグイン**は、lync 2013 向けに開発されたもので、仮想デスクトップで実行されている lync 2013 または Skype for business 2015 クライアントと互換性があります。 ローカルコンピューターにインストールされるスタンドアロンアプリケーションであり、仮想デスクトップ上のクライアントでローカルのオーディオデバイスとビデオデバイスを使用できます。 このプラグインでは、ローカルコンピューターまたはシンクライアントに Skype for Business クライアントをインストールする必要はありません。これには、Windows 7、Windows 8、または Windows Server 2008 オペレーティングシステムを実行する必要があります。 (以下のオペレーティングシステムを使用し、Microsoft がサポートしているシンクライアントデバイス: Dell Wyse Z90D7、dell Wyse R90L7、Dell Wyse X90m7、HP t610、HP t5740e)。このプラグインは引き続きサポートされますが、今後の更新プログラムは計画されません。 Citrix ベースの仮想環境では、Citrix リアルタイム最適化パックをお勧めします。
    
- **Citrix リアルタイム最適化パック**は、lync VDI プラグインに基づいて作成され、仮想デスクトップ上の lync 2013 または Skype for business 2016 クライアントと連携して動作します。 この機能は、従来の VDI プラグインの改善のために、Citrix と Microsoft によって共同開発されました。 Windows と Windows 以外のオペレーティングシステム (Windows 10、Mac、Linux を含む) がインストールされているクライアントにインストールできます。 これは、リアルタイムコネクタ (仮想デスクトップにインストールされている) とリアルタイムメディアエンジン (エンドユーザーのローカルコンピューターにインストールされている) の2つのコンポーネントで構成されます。 この2つのコンポーネントによって、ユーザーのローカルコンピューターは、仮想デスクトップで実行されている Skype for Business クライアントを、A/V 処理をローカルコンピューターに移動して使うことができます。 Citrix ベースの仮想デスクトップ環境では、Citrix リアルタイム最適化パックをお勧めします。さらにサポートが計画されています。
    
- Skype for Business 向け**Vmware ホライズン仮想化パック**は、vmware との共同作業によって開発された skype for business を仮想デスクトップで提供しながら、優れたユーザーエクスペリエンスを提供します。 このソリューションは、クライアントでのメディア エンジンを活用することによって最適なソリューションを作り出し、音声通話やビデオ通話に対するメディア オフロード機能を提供するクライアント エンドポイントとともに機能します。 このソリューションは、1対1のコラボレーションのエンドポイント間で直接オーディオとビデオを配信したり、マルチパーティの会議通話や会議の中央の Multipoint コントロールユニット (MCU) にオフロードしたりすることができます。
    
> [!NOTE]
> Skype for Business Basic クライアントは、Citrix HDX リアルタイム最適化パックまたは VMWare ホライズン仮想化パックでサポートされていません。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix の VDI 環境プラグイン (XenApp と XenDesktop の機能) は、Lync 2013 および Skype for Business 2015 および 2016 (任意のクリックでインストーラーを実行する完全なクライアント、または仮想にインストールされ2017た MSI インストーラー) と互換性があります。デスクトップ. 全体的な機能は、Microsoft Lync VDI プラグインをベースにしていますが、Windows 10、Macintosh、Linux など、幅広いクライアントオペレーティングシステムで動作します。
  
すべての機能とサポートされるテクノロジの一覧は、 [Microsoft Skype For business を XenApp および XenDesktop ユーザーに配信する](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)ときに、Citrix の web サイトで参照できます。
  
詳細については、次のリンクを参照してください。
  
- Citrix [HDX リアルタイム最適化パック 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business の機能のサポート](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

VMWare の VDI 環境ソリューションは、仮想デスクトップにインストールされた Skype for Business 2015 および2016フルクライアントと互換性があります。 全体的な機能は、Microsoft Lync VDI プラグインをベースにしていますが、Windows 10、Macintosh、Linux など、幅広いクライアントオペレーティングシステムで動作します。 
  
機能およびサポートされる技術については、次のリンク先にある VMWare Web サイトで詳細に取り上げられています。
  
- [VMware ホライズン 7.4 &amp;ホライズンクライアント4.7 の新機能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Skype for Business 用のホライズン仮想化パック](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business (VMWare ホライズン)](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>マイクロソフトの Lync VDI プラグイン
<a name="Citrix_RT"> </a>

Microsoft Lync VDI プラグインソリューションを使用する場合、ユーザーは Windows コンピューターまたはシンクライアント上に存在し、仮想デスクトップ上のクライアントからの音声/ビデオストリームを処理するために Microsoft の Lync VDI プラグインがインストールされている必要があります。 具体的な操作は次のとおりです。
  
1. 音声/ビデオ デバイス (ヘッドセットやカメラ) をローカル コンピューターに接続します。
    
2. Lync 2013 または Skype for Business 2015 クライアントを使ってリモート仮想デスクトップに接続します。
    
3. 仮想デスクトップ上の Skype for Business の資格情報を入力します。
    
4. ユーザー資格情報を再入力して、ローカルの Windows コンピューターまたはシンクライアントで Lync VDI プラグインとの接続を確立します。
    
接続が確立されたら、音声やビデオの通話を受信する準備が整います。ローカル コンピューターが音声/ビデオ処理を行うため、ネットワーク上のトラフィックと仮想デスクトップの負荷は最小限になります。
  
Microsoft Lync VDI プラグインは、特定の Windows オペレーティングシステムでのみサポートされ、Lync 2013 または Skype for Business 2015 クライアントでのみサポートされます。 サポートされる技術と制限の詳細については、「[サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- [サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)
    
- [Lync VDI プラグインの前提条件](vdi-environments.md#VDI_prereq)
    
- [Lync VDI プラグインを Skype for Business Server と共に展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix ナレッジセンターの記事[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI プラグインは、 [Microsoft LYNC vdi 2013 プラグイン (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)または[microsoft lync vdi 2013 プラグイン (64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)で利用できます。 このプラグインは、名前にもかかわらず、Skype for Business 2015 クライアントでサポートされています。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>サポートされる仮想化テクノロジと既知の制限
<a name="Supported_virt"> </a>

Lync VDI プラグインを使うと、サポートされている仮想化テクノロジで音声とビデオ通話を行うことができます。 標準的な電話の規制に準拠するため、E911 のサポートも含まれています。 以下のセクションでは、Lync VDI プラグインでサポートされている仮想化テクノロジと既知の機能の制限について説明します。
  
#### <a name="support-for-virtualization-technologies"></a>サポートされている仮想化テクノロジ

Lync VDI プラグインは、個人用仮想デスクトップシナリオでは完全なデスクトップリモートセッションをサポートしますが、リモートデスクトップセッションのシナリオではサポートしていません。 これらのシナリオは、次のように記述できます。
  
- **サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップインフラストラクチャ (VDI)。** このシナリオでは、各ユーザーがカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存することができます。 Microsoft リモートデスクトップサービスと VMware ホライズンビューは、Skype for Business 2015 で使用することがテストされた実装の例です。 検証対象のその他の実装には、Citrix XenDesktop が含まれています。 Microsoft によってテストされたベンダー固有の VDI 環境とクライアントハードウェアの詳細については、「 [Microsoft Lync のインフラストラクチャ認定](https://go.microsoft.com/fwlink/?LinkID=313435)」を参照してください。
    
- **サポートされないシナリオ: リモート デスクトップ セッション。** このシナリオでは、各ユーザーはカスタマイズできない汎用の仮想デスクトップ セッションにログオンします。 たとえば、Microsoft リモートデスクトップセッション (RDSH) と Citrix XenApp を Citrix レシーバーと組み合わせることができます。
    
Lync VDI プラグインは、アプリケーションの仮想化などの他の仮想化テクノロジをサポートしていません。これにより、完全なアプリケーションをローカルでインストールする必要なく、アプリケーションを使用できるようになります。 実装の例には、Citrix XenApp と Microsoft Application Virtualization (App-v) が含まれます。 アプリケーションのストリーミング、アプリケーションのリモート処理、および混合型の仮想化モード (たとえば、完全なデスクトップリモート処理におけるアプリケーションのリモート処理) はサポートされていません。
  
Lync VDI プラグインは、動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使用するように設計されています。 明示的にサポートされていないシナリオについては、「VDI ソリューションプロバイダーのサポートステートメント」を参照してください。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI プラグインの前提条件
<a name="VDI_prereq"> </a>

VDI 環境では、仮想マシンとユーザーのローカルコンピューターがこのセクションで示されている要件を満たしている必要があります。
  
> [!NOTE]
>  環境のインストール方法および展開方法の詳細については、仮想化ソリューション プロバイダーにお問い合わせください。 Hyper-v とリモートデスクトップサービスに基づく仮想環境の展開に関する一般的な情報については、Microsoft Library: [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 のリモートデスクトップサービス](https://go.microsoft.com/fwlink/p/?linkid=247513)の次の記事を参照してください。 
  
仮想マシンは、最新の service pack を使用して、Windows 8、Windows 7、または Windows Server 2008 R2 で構成する必要があります。
  
ユーザーのローカルコンピューターは、次の要件を満たしている必要があります。
  
- ユーザーは、Skype for Business Server または Lync Server 2013 を使用している必要があります。
    
- ローカルコンピューターは、SP1、Windows 7 SP1、または Windows 8 で Windows Embedded 標準7を実行している必要があります。
    
- リモートデスクトップサービスを使用している場合は、ローカルコンピューターのオペレーティングシステムに合わせて、32ビットまたは64ビットの Lync VDI プラグインを選択します。 ローカル コンピューターと仮想マシンの両方に 32 ビットまたは 64 ビットのオペレーティング システムをインストールしておく必要はありません。 別の仮想化ソリューションやプラットフォームを使用している場合は、プロバイダーの要件を参照してください。
    
- ローカルコンピューターで、[最新バージョンのリモートデスクトップクライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)が実行されている必要があります。 Microsoft からリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 
    
- ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート レコーディングが無効となるように構成する必要があります。 Windows でリモートデスクトップ接続のこれらの設定を構成するには、次のセクション「リモートデスクトップ接続設定を構成する」を参照してください。 
    
Microsoft VDI プラグインは、 [Microsoft LYNC vdi 2013 プラグイン (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)または[microsoft lync vdi 2013 プラグイン (64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)で利用できます。
  
#### <a name="known-feature-limitations"></a>既知の機能制限
<a name="VDI_prereq"> </a>

VDI 環境で Skype for Business 2015 クライアントを使用する場合は、次のような制限があります。
  
通話の委任と応答グループのエージェント匿名化) 機能は、制限されています。
  
以下の機能はサポートされません。
  
- 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
- マルチビュー ビデオ
    
- 会話の録音
    
- 会議への匿名参加 (つまり、組織とフェデレーションされていない組織によってホストされている Skype for Business 会議への参加)。
    
- Lync VDI プラグインと Lync Phone Edition デバイスの併用。
    
- ネットワーク停止時の通話の継続
    
- 保留機能の着信音と音楽のカスタマイズ
    
Lync VDI プラグインは、Office 365 環境ではサポートされていません。
  
> [!NOTE]
> Citrix RealTime Optimization Pack は、Office 365 をサポートしています。 Citrix ベースの仮想環境については、サポートされている機能とバージョンのリストについて、Citrix の[技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)ドキュメントを確認してください。
  
## <a name="see-also"></a>関連項目
<a name="Citrix_RT"> </a>

[Lync VDI プラグインを Skype for Business Server と共に展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

