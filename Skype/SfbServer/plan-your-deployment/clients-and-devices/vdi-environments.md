---
title: VDI 環境での Skype for Business の計画
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
description: このトピックでは、リモートの仮想デスクトップに接続しているときに Skype for Business を使用する際の計画に関する考慮事項について説明します。
ms.openlocfilehash: c2972e2b453b6cf5592ddc8b3b48dfceee9a4e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027998"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 環境での Skype for Business の計画
 
このトピックでは、リモートの仮想デスクトップに接続しているときに Skype for Business を使用する際の計画に関する考慮事項について説明します。 
  
仮想デスクトップインフラストラクチャ (VDI) 環境は、セキュリティおよびコンプライアンスの問題が特に重要である一部の組織で使用されます。 ユーザーは、リモートデスクトップサービスまたは同様のリモート接続を使用して、すべてのデスクトップアプリケーションとファイルで仮想デスクトップ上で作業を行います。 仮想デスクトップに所属するクライアントで、オーディオとビデオの処理の負荷が増大しなければならないような接続で、Skype for Business を使用して、オーディオとビデオを完全に統合することができます。 その処理をエンドユーザーのローカルコンピューターにオフロードし、仮想デスクトップの負荷を軽減する、追加の VDI プラグインソフトウェアが用意されています。
  
VDI プラグインコンポーネントには、Microsoft、Citrix、VMWare で提供される3つのソリューションが用意されています。 新しい展開の場合、Citrix HDX リアルタイム最適化パックソリューションまたは VMWare ホライズン仮想化パックのどちらかを使用することをお勧めします。 元の Lync VDI プラグインは、そのライフサイクルの残りの部分でまだサポートされています。
  
- Lync **VDI プラグイン**は lync 2013 用に開発され、仮想デスクトップ上で実行されている lync 2013 または Skype for business 2015 クライアントのどちらかと互換性があります。 これはスタンドアロンアプリケーションで、ローカルコンピューターにインストールされ、仮想デスクトップ上のクライアントでローカルのオーディオおよびビデオデバイスを使用することができます。 このプラグインでは、ローカルコンピューターまたはシンクライアントに Skype for Business クライアントをインストールする必要はありません。これには、Windows 7、Windows 8、または Windows Server 2008 オペレーティングシステムを実行する必要があります。 (これらのオペレーティングシステムを使用し、Microsoft によってサポートされているシンクライアントデバイスには、Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610、HP t5740e) があります。このプラグインはまだサポートされていますが、今後の更新プログラムは予定されていません。 Citrix ベースの仮想環境の場合、Citrix リアルタイム最適化パックを使用することをお勧めします。
    
- **Citrix リアルタイム最適化パック**は、lync VDI プラグインに基づいて作成され、仮想デスクトップ上の lync 2013 または Skype for business 2016 クライアントで動作します。 これは、従来の VDI プラグインを改善するために Citrix と Microsoft によって共同開発されました。 Windows および windows 以外のオペレーティングシステム (Windows 10、Mac、Linux を含む) がインストールされているクライアントにインストールできます。 これは、リアルタイムコネクタ (仮想デスクトップにインストールされる) とリアルタイムメディアエンジン (エンドユーザーのローカルコンピューターにインストールされている) の2つのコンポーネントで構成されています。 この2つのコンポーネントを使用すると、ユーザーのローカルコンピューターは、ローカルコンピューターに音声ビデオ処理を移動することで、仮想デスクトップ上で実行されている Skype for Business クライアントを使用することができます。 Citrix ベースの仮想デスクトップ環境では、Citrix リアルタイム最適化パックが推奨されており、さらにサポートが計画されています。
    
- Vmware とのコラボレーションで開発された Skype for business 用**Vmware ホライズン仮想化パック**を使用すると、優れたユーザー環境を提供しながら、仮想デスクトップで Skype for business を提供することができます。 このソリューションでは、クライアントのメディアエンジンを使用して最適化されたソリューションを作成し、クライアントエンドポイントで音声およびビデオ通話用のメディアオフロード機能を提供します。 1対1のコラボレーションのためのエンドポイント間での音声とビデオの配信、またはマルチパーティの電話会議または会議のために中央の Multipoint Control Unit (MCU) にオフロードできる、このソリューション。
    
> [!NOTE]
> Skype for Business Basic クライアントは、Citrix HDX リアルタイム最適化パックまたは VMWare ホライズン仮想化パックではサポートされていません。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX リアルタイム最適化パック
<a name="Citrix_RT"> </a>

Citrix の VDI 環境プラグイン (XenApp および XenDesktop の機能) は、Lync 2013 と Skype for Business 2015 および 2016 (任意のクリックでインストーラーを実行するための完全なクライアント、または仮想サーバーにインストールされた1月 2017 PU の後にリリースされた MSI インストーラー) と互換性があります。コンピューター. 全体的な機能は Microsoft Lync VDI プラグインに基づいていますが、Windows 10、Macintosh、Linux を含む、幅広いクライアントオペレーティングシステムで動作します。
  
機能とサポートされるテクノロジの完全な一覧については、「 [Microsoft Skype For business を XenApp および XenDesktop ユーザーに提供](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)する」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- Citrix [HDX リアルタイム最適化パック 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business 機能のサポート](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare ホライズン仮想化パック
<a name="Citrix_RT"> </a>

VMWare の VDI 環境ソリューションは、仮想デスクトップにインストールされた Skype for Business 2015 および2016の完全なクライアントと互換性があります。 全体的な機能は Microsoft Lync VDI プラグインに基づいていますが、Windows 10、Macintosh、Linux を含む、幅広いクライアントオペレーティングシステムで動作します。 
  
機能とサポートされているテクノロジの詳細については、以下のリンクにある VMWare web サイトを参照してください。
  
- [VMware ホライズン 7.4 &amp;ホライズンクライアント4.7 の新機能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Skype for Business 用のホライズン仮想化パック](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [VMWare ホライズンを使用した Microsoft Skype for Business](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft の Lync VDI プラグイン
<a name="Citrix_RT"> </a>

Microsoft Lync VDI プラグインソリューションでは、ユーザーは Windows コンピューターまたはシンクライアント上にあり、仮想デスクトップ上のクライアントからの音声ビデオストリームを処理するために Microsoft の Lync VDI プラグインがインストールされている必要があります。 ユーザーは次のようになります。
  
1. 音声ビデオデバイス (ヘッドセットやカメラなど) をローカルコンピューターに接続します。
    
2. Lync 2013 または Skype for Business 2015 クライアントを使用してリモート仮想デスクトップに接続します。
    
3. 仮想デスクトップ上の Skype for Business の資格情報を入力します。
    
4. ユーザー資格情報を再入力して、ローカルの Windows コンピューターまたはシンクライアントで Lync VDI プラグインとの接続を確立します。
    
接続が確立されると、ユーザーは音声およびビデオ通話を発信および受信できるようになります。 ローカルコンピューターが音声/ビデオ処理を処理するため、ネットワーク上のトラフィックと仮想デスクトップの負荷は最小化されます。
  
Microsoft の Lync VDI プラグインは、特定の Windows オペレーティングシステムでのみサポートされており、Lync 2013 または Skype for Business 2015 クライアントのみをサポートします。 サポートされているテクノロジと制限の詳細については[、「サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)」を参照してください。
  
詳細については、次のリンクを参照してください。
  
- [サポートされる仮想化テクノロジと既知の制限](vdi-environments.md#Supported_virt)
    
- [Lync VDI プラグインの前提条件](vdi-environments.md#VDI_prereq)
    
- [Skype for Business Server を使用して Lync VDI プラグインを展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix ナレッジセンターの記事[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI プラグインは、 [Microsoft LYNC vdi 2013 プラグイン (32 ビット)](https://www.microsoft.com/download/details.aspx?id=35457)または[microsoft lync vdi 2013 plugin (64 ビット)](https://www.microsoft.com/download/details.aspx?id=35454)から入手できます。 このプラグインは、名前にかかわらず、Skype for Business 2015 クライアントでサポートされています。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>サポートされる仮想化テクノロジと既知の制限
<a name="Supported_virt"> </a>

Lync VDI プラグインは、サポートされている仮想化テクノロジに対して音声およびビデオ通話を許可します。 標準電話の規制に準拠するには、E911 のサポートも含まれています。 次のセクションでは、Lync VDI プラグインによってサポートされる仮想化テクノロジと既知の機能制限について説明します。
  
#### <a name="support-for-virtualization-technologies"></a>仮想化テクノロジのサポート

Lync VDI プラグインは、個人用仮想デスクトップシナリオでは完全なデスクトップリモートセッションをサポートしますが、リモートデスクトップセッションシナリオではサポートしていません。 これらのシナリオは、次のように記述できます。
  
- **サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップインフラストラクチャ (VDI)。** このシナリオでは、ユーザーごとにカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存することができます。 Microsoft リモートデスクトップサービスおよび VMware のホライズン表示では、Skype for Business 2015 での使用をテストした実装の例を示します。 検証を行うその他の実装には、Citrix XenDesktop が含まれます。 Microsoft によってテストされたベンダー固有の VDI 環境およびクライアントハードウェアの詳細については、「 [Microsoft Lync 用のインフラストラクチャ認定](https://go.microsoft.com/fwlink/?LinkID=313435)」を参照してください。
    
- **サポート対象外: リモートデスクトップセッション。** このシナリオでは、ユーザーごとに、カスタマイズできない汎用の仮想デスクトップセッションにログオンします。 たとえば、Microsoft リモートデスクトップセッション (RDSH) と citrix XenApp を Citrix 受信者と組み合わせて使用することができます。
    
Lync VDI プラグインは、アプリケーションの仮想化などの他の仮想化テクノロジをサポートしていません。これにより、完全なアプリケーションをローカルにインストールすることなく、アプリケーションを使用できるようになります。 実装の例としては、Citrix XenApp と Microsoft Application Virtualization (App-v) があります。 アプリケーションのストリーミング、アプリケーションのリモート処理、および混合仮想化モード (たとえば、完全なデスクトップリモート処理でのアプリケーションのリモート処理) はサポートされていません。
  
Lync VDI プラグインは、動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使用するように設計されています。 明示的にサポートされていないシナリオについては、「VDI ソリューションプロバイダーからのサポートステートメント」を参照してください。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI プラグインの前提条件
<a name="VDI_prereq"> </a>

VDI 環境では、仮想マシンとユーザーのローカルコンピューターが、このセクションで説明されている要件を満たしている必要があります。
  
> [!NOTE]
>  仮想化ソリューションプロバイダーは、環境をインストールして展開する方法の詳細を提供できます。 Hyper-v およびリモートデスクトップサービスに基づく仮想環境の展開に関する一般的な情報については、「Microsoft Library: [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)、[リモートデスクトップサービス (Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) )」の次の記事を参照してください。 
  
仮想マシンは、最新のサービスパックを使用して Windows 8、windows 7、または Windows Server 2008 R2 を使用して構成する必要があります。
  
ユーザーのローカルコンピューターは、次の要件を満たしている必要があります。
  
- ユーザーは、Skype for Business Server または Lync Server 2013 に所属している必要があります。
    
- ローカルコンピューターでは、Windows Embedded Standard 7 SP1、Windows 7 SP1、または Windows 8 を実行している必要があります。
    
- リモートデスクトップサービスを使用している場合は、ローカルコンピューターのオペレーティングシステムと一致するように、32ビットまたは64ビットの Lync VDI プラグインを選択します。 ローカルコンピューターと仮想マシンの両方に32ビットまたは64ビットのオペレーティングシステムがインストールされている必要はありません。 別の仮想化ソリューションまたはプラットフォームを使用している場合は、プロバイダーの要件を参照してください。
    
- ローカルコンピューターは、[最新バージョンのリモートデスクトップクライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)を実行している必要があります。 マイクロソフトからリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。 
    
- ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート録音が無効となるように構成する必要があります。 Windows でこれらの設定をリモートデスクトップ接続用に構成するには、次のセクション「リモートデスクトップ接続の設定を構成するには」を参照してください。 
    
Microsoft VDI プラグインは、 [Microsoft LYNC vdi 2013 プラグイン (32 ビット)](https://www.microsoft.com/download/details.aspx?id=35457)または[microsoft lync vdi 2013 plugin (64 ビット)](https://www.microsoft.com/download/details.aspx?id=35454)から入手できます。
  
#### <a name="known-feature-limitations"></a>既知の機能制限
<a name="VDI_prereq"> </a>

VDI 環境で Skype for Business 2015 クライアントを使用する場合の既知の制限事項は次のとおりです。
  
通話委任および応答グループエージェント匿名化機能のサポートには制限があります。
  
以下の機能はサポートされません。
  
- 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
- マルチビュービデオ。
    
- 会話の録音
    
- 匿名での会議への参加 (つまり、組織とフェデレーションされない組織によってホストされている Skype for Business 会議への参加)。
    
- Lync VDI プラグインを Lync Phone Edition デバイスと共に使用します。
    
- ネットワーク停止時の通話の継続
    
- カスタマイズされた着信音と音楽の保持機能。
    
Lync VDI プラグインは、Office 365 環境ではサポートされていません。
  
> [!NOTE]
> Citrix リアルタイム最適化パックは Office 365 をサポートしています。 Citrix ベースの仮想環境の場合は、サポートされている機能とバージョンの一覧について、Citrix の[技術概要](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)のドキュメントを参照してください。
  
## <a name="see-also"></a>関連項目
<a name="Citrix_RT"> </a>

[Skype for Business Server を使用して Lync VDI プラグインを展開する](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

