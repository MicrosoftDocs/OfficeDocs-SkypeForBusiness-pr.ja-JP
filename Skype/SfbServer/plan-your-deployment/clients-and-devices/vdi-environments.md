---
title: VDI 環境における Skype for Business の計画
author: jambirk
ms.author: jambirk
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: このトピックでは、リモート仮想デスクトップへの接続中に、ビジネスの Skype を使用するための計画に関する考慮事項について説明します。
ms.openlocfilehash: 0d24426ea661e5a2d445e4fd7ef90d6a41518692
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207252"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 環境における Skype for Business の計画
 
このトピックでは、リモート仮想デスクトップへの接続中に、ビジネスの Skype を使用するための計画に関する考慮事項について説明します。 
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。 作業は、Remote Desktop Services または同様のリモート接続を使用して、すべてのデスクトップ アプリケーションとファイルを使用して、仮想デスクトップで行われます。 ビジネスの Skype を使用すると、完全にオーディオとビデオ接続ではそのような必要がありますオーディオの負荷が高いと、仮想デスクトップ クライアントで処理するビデオが置かれています。 VDI の追加のプラグイン ソフトウェアが利用可能なをエンド ・ ユーザーのローカル マシンには、その処理の負荷を軽減し、仮想デスクトップ上の負荷を軽減します。
  
VDI プラグイン コンポーネントで使用できるソリューションには、マイクロソフト、Citrix、VMware が提供する 3 つのソリューションがあります。 新しい展開では、Citrix HDX のリアルタイム最適化パック ソリューションまたは地平線の VMWare 仮想化パックのいずれかの使用をお勧めします。 元のプラグインの Lync VDI は、情報ライフ サイクルの残りの部分は引き続きサポートされます。
  
- **プラグインの Lync VDI** Lync 2013 用に開発され、の互換性が Lync 2013 または Skype ビジネス 2015年クライアントが仮想デスクトップで実行されているのです。 スタンドアロンのアプリケーションをローカル コンピューター上にインストールし、仮想デスクトップ上のクライアントでローカルのオーディオおよびビデオ デバイスの使用を許可することをお勧めします。 プラグインは必要ありません、Skype のビジネスのクライアント、ローカル コンピューターまたは Windows 7、Windows 8 の場合、または Windows Server 2008 オペレーティング システムを実行する必要がありますが、シン ・ クライアントにインストールされています。 (これらのオペレーティング システムを使用して、マイクロソフトによってサポートされている、シン クライアント デバイスが含まれます: Dell Wyse Z90D7、Dell の Wyse R90L7、Wyse X90m7 のデル、HP t610、および HP t5740e)。このプラグインはまだサポートされているが、将来の更新が予定されていません。 Citrix ベースの仮想環境の Citrix のリアルタイム最適化パックの使用をお勧めします。
    
- **Citrix リアルタイム最適化パック**Lync VDI のプラグインのビルドで、Lync 2013 または Skype ビジネス 2016年クライアントの仮想デスクトップにいます。 プラグインの元の VDI 改善のために、Citrix と Microsoft によって開発された共同。 Windows と Windows 以外のオペレーティング システムが (10 の Windows、Mac および Linux を含む) をクライアントにインストールできます。 2 つのコンポーネントで構成されています: リアルタイム、コネクタ (仮想デスクトップにインストールされている) と、リアルタイム メディア エンジン (これは、エンド ・ ユーザーのローカル コンピューターにインストールされている)。 これら 2 つのコンポーネントを使用すると、ビジネス クライアントが、仮想デスクトップ上で、A を実行するため、Skype を使用するローカル コンピューターのユーザーの V の処理がローカル コンピューターに移動したとします。 Citrix ベースの仮想デスクトップ環境、Citrix のリアルタイム最適化パックを使用することをお勧めし、さらにサポートが予定されています。
    
- VMWare とのコラボレーションで開発したビジネス用の Skype の**VMWare 水平仮想化パック**を使用すると、仮想デスクトップで、優れたユーザー エクスペリエンスを提供しながらビジネスの Skype を提供します。 このソリューションは、クライアントでのメディア エンジンを活用することによって最適なソリューションを作り出し、音声通話やビデオ通話に対するメディア オフロード機能を提供するクライアント エンドポイントとともに機能します。 いずれか 1 対 1 の共同作業のためのエンドポイント間で直接、オーディオとビデオを配信したりする、中心的なマルチポイント コントロール ユニット (MCU) マルチパーティの会議または会議の負荷を軽減するソリューションです。
    
> [!NOTE]
> Citrix HDX のリアルタイム最適化パックまたは地平線の VMWare 仮想化パックでは、ビジネスの基本的なクライアントの Skype はサポートされていません。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix 社の VDI 環境のプラグイン (XenApp と XenDesktop の機能) は、Lync 2013 およびビジネス 2015年、2016 (全クライアントを使用して、インストーラー、または年 2017年 1 月 PU 以降後にリリースされた MSI インストーラーを実行する) クライアントが、仮想にインストールされている Skype との互換性デスクトップです。 全体的な機能は、Microsoft Lync VDI のプラグインですが、10 の Windows、Macintosh、Linux など、クライアントのオペレーティング システムの広範な機能に基づいています。
  
[XenApp と XenDesktop のユーザーにビジネスのマイクロソフトの提供する Skype](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)の Citrix web サイトのすべての機能とサポートされているテクノロジの一覧が見つかります。
  
詳細については、次のリンクを参照してください。
  
- Citrix [HDX リアルタイム最適化パック 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [ビジネス機能をサポートするための CTX200279 Skype](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

VMWare VDI 環境のソリューションは、ビジネス 2015年、2016 の全クライアントが仮想デスクトップにインストールされている Skype と互換性があります。 全体的な機能は、Microsoft Lync VDI のプラグインですが、10 の Windows、Macintosh、Linux など、クライアントのオペレーティング システムの広範な機能に基づいています。 
  
機能およびサポートされる技術については、次のリンク先にある VMWare Web サイトで詳細に取り上げられています。
  
- [VMware 地平線 7.4 の新機能&amp;水平クライアント 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [ビジネスの Skype の地平線の仮想化パック](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [VMWare の地平線との取引にマイクロソフトの Skype](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>マイクロソフトの Lync VDI プラグイン
<a name="Citrix_RT"> </a>

ソリューションでは、Microsoft Lync VDI プラグイン、ユーザーが、Windows コンピューターまたはシン クライアントにインストールして、仮想デスクトップ上のクライアントからのオーディオ/ビデオ ストリームを処理するためにインストールされているマイクロソフトの Lync VDI のプラグインがあります。 具体的な操作は次のとおりです。
  
1. 音声/ビデオ デバイス (ヘッドセットやカメラ) をローカル コンピューターに接続します。
    
2. Lync 2013 または Skype ビジネス 2015年クライアントのリモート仮想デスクトップに接続します。
    
3. ビジネス用の Skype の仮想デスクトップの資格情報を入力します。
    
4. Lync VDI が Windows のローカル コンピューターまたはシン クライアントのプラグインとの接続を確立するためにユーザーの資格情報を再入力します。
    
接続が確立されたら、音声やビデオの通話を受信する準備が整います。ローカル コンピューターが音声/ビデオ処理を行うため、ネットワーク上のトラフィックと仮想デスクトップの負荷は最小限になります。
  
マイクロソフトの Lync VDI のプラグインは、特定の Windows オペレーティング システムでのみサポートし、のみビジネス 2015年クライアント Lync 2013 または Skype をサポートしています。 サポートされる技術と制限の詳細については、「[サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- [サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)
    
- [Lync VDI プラグインの前提条件](vdi-environments.md#VDI_prereq)
    
- [ビジネス サーバーの Skype では、プラグインの Lync VDI の導入します。](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix サポート技術情報センターの記事[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI のプラグインは、 [Microsoft Lync VDI 2013 プラグイン (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) 、または[Microsoft Lync VDI 2013 プラグイン (64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)で使用できます。 ビジネス 2015年クライアントは、名前にかかわらず、Skype では、このプラグインがサポートされます。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>サポートされる仮想化テクノロジと既知の制限
<a name="Supported_virt"> </a>

Lync VDI のプラグインには、オーディオとビデオのサポートされている仮想化テクノロジを呼び出すことができます。 標準的な電話の規制に準拠してサポート E911 も含まれます。 次のセクションでは、プラグインの Lync VDI と既知の機能の制限でサポートされている仮想化テクノロジについて説明します。
  
#### <a name="support-for-virtualization-technologies"></a>サポートされている仮想化テクノロジ

プラグインの Lync VDI では、リモート デスクトップ セッションではありませんが、個人用仮想デスクトップの場合、完全なデスクトップのリモート セッションをサポートしています。 これらのシナリオは、次のように記述できます。
  
- **サポートされています。 個人用仮想デスクトップまたは仮想デスクトップ インフラストラクチャ (VDI) に設定しました。** このシナリオでは、各ユーザーは、カスタマイズ可能な仮想デスクトップにログオンしたときにされ、セッション間で保持するデスクトップ上のファイルを保存することです。 Microsoft リモート デスクトップ サービスと VMware の水平のビューは、ビジネス 2015年の Skype で使用するためにテストされている実装の例です。 検証中であるため、他の実装には、Citrix XenDesktop が含まれています。 VDI 環境の特定のベンダーと Microsoft によってテストされているクライアントのハードウェアについては、[インフラストラクチャが Microsoft Lync の修飾](https://go.microsoft.com/fwlink/?LinkID=313435)を参照してください。
    
- **サポートされないシナリオ: リモート デスクトップ セッション。** このシナリオでは、各ユーザーはカスタマイズできない汎用の仮想デスクトップ セッションにログオンします。 例としては、Microsoft リモート デスクトップ セッション (RDSH) と、Citrix XenApp は、Citrix の受信機と組み合わせます。
    
Lync VDI のプラグインは、ローカルでの完全なアプリケーションのインストールを必要とせず、アプリケーションの使用は、アプリケーションの仮想化など、他の仮想化テクノロジをサポートしていません。 実装例には、Citrix XenApp とマイクロソフト アプリケーションの仮想化 (APP-V) が含まれます。 アプリケーションのストリーミング、アプリケーションのリモート処理、および仮想化の混在モード (たとえば、アプリケーションでのリモート処理完全なデスクトップのリモート処理) はサポートされていません。
  
Lync VDI のプラグインは、動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使用するよう設計されました。 明示的にサポートされていないシナリオでは、VDI ソリューション ・ プロバイダーからのステートメントをサポートするために参照してください。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI プラグインの前提条件
<a name="VDI_prereq"> </a>

VDI 環境でバーチャル マシン、およびユーザーのローカル コンピューターは、このセクションで概説する要件を満たす必要があります。
  
> [!NOTE]
>  環境のインストール方法および展開方法の詳細については、仮想化ソリューション プロバイダーにお問い合わせください。 HYPER-V とリモート デスクトップ サービスに基づく仮想化環境の展開に関する一般的な情報は、Microsoft のライブラリでは、以下の資料を参照してください: [HYPER-V で](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 でのリモート デスクトップ サービス](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
最新のサービス パックで Windows 8 の、Windows 7 または Windows Server 2008 R2 でバーチャル マシンを構成しなければなりません。
  
ユーザーのローカル コンピューターでは、次の要件を満たす必要があります。
  
- ビジネス サーバーまたは Lync Server 2013 の Skype のユーザーが所属する必要があります。
    
- ローカル コンピューターが SP1、SP1、または Windows 8 と Windows 7 と Windows の組み込みの標準的な 7 を実行しなければなりません。
    
- リモート デスクトップ サービスを使用する場合は、32 ビットまたは 64 ビット Lync VDI プラグインをローカル コンピューターのオペレーティング ・ システムを一致を選択します。 ローカル コンピューターと仮想マシンの両方に 32 ビットまたは 64 ビットのオペレーティング システムをインストールしておく必要はありません。 別の仮想化ソリューションやプラットフォームを使用している場合は、プロバイダーの要件を参照してください。
    
- ローカル コンピューターでは、[リモート デスクトップ クライアントの最新バージョン](https://go.microsoft.com/fwlink/p/?LinkId=268032)を実行している必要があります。 Microsoft からリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 
    
- ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート レコーディングが無効となるように構成する必要があります。 Windows でこれらの設定をリモート デスクトップ接続を構成、次のセクション、「リモート デスクトップ接続の設定を構成します。」を参照してください。 
    
Microsoft VDI のプラグインは、 [Microsoft Lync VDI 2013 プラグイン (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) 、または[Microsoft Lync VDI 2013 プラグイン (64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)で使用できます。
  
#### <a name="known-feature-limitations"></a>既知の機能制限
<a name="VDI_prereq"> </a>

次のような制限、VDI 環境でのビジネス 2015年のクライアントに、Skype を使用する場合。
  
委任の呼び出し、および応答グループのエージェントの匿名の機能を限定的にサポートがあります。
  
以下の機能はサポートされません。
  
- 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
- マルチビュー ビデオ
    
- 会話の録音
    
- 会議に参加する匿名では、結合する Skype ビジネス会議の組織とフェデレーションを行うしていない組織でホストされているため)。
    
- Lync の電話のエディションのデバイスとプラグインの Lync VDI を使用しています。
    
- ネットワーク停止時の通話の継続
    
- 保留機能の着信音と音楽のカスタマイズ
    
Lync VDI のプラグインは、Office 365 環境ではサポートされていません。
  
> [!NOTE]
> Citrix RealTime Optimization Pack は、Office 365 をサポートしています。 Citrix ベースの仮想環境の場合、サポートされている機能とバージョンの一覧については citrix 社の[技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)マニュアルを参照してください。
  
## <a name="see-also"></a>関連項目
<a name="Citrix_RT"> </a>

[ビジネス サーバーの Skype では、プラグインの Lync VDI の導入します。](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

