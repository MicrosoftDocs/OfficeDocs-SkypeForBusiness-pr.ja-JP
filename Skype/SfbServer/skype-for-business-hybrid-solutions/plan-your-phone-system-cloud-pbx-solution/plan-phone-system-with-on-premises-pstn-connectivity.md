---
title: Skype で設置した PSTN 接続を持つビジネス サーバーの Office 365 の電話システムを計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 設置 PSTN への接続では、Office 365 (クラウド PBX) の電話システムの計画の考慮事項について説明します。
ms.openlocfilehash: 978da546961188c54c7e08e2ed140f8d01986e44
ms.sourcegitcommit: 20defe18ac1d2b21853bd6d5f0772cd3f35e53e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "29686473"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype で設置した PSTN 接続を持つビジネス サーバーの Office 365 の電話システムを計画します。

設置 PSTN への接続では、Office 365 (クラウド PBX) の電話システムの計画の考慮事項について説明します。

このコンテンツは、または場合は既に Skype ビジネス サーバーに Lync Server 2013 の設置型の展開に関連します。 その他のシナリオでは、 [Microsoft のテレフォニー ソリューション](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)を参照してください。

 設置 PSTN への接続と Office 365 の電話システムでは、ユーザーの電話システム (PBX をクラウド) 機能を活用を行うことができます。 これは、次のようなシナリオで役立ちます。

- ビジネス ユーザー ホーム設置型、Skype のいくつかがある場合、他の人所属している Skype のオンライン ビジネスの。 Office 365 の機能で電話システムを有効にでき、ユーザー向けの機能がビジネス オンラインでは、Skype でホームしますが、設置した PSTN 接続を使用し続けます。

- 設置型展開があるし、するが、Skype をオンライン ビジネスの一部またはすべてのユーザーを移動、設置した PSTN 接続を使用し続けます。

    > [!IMPORTANT]
    > 正常に有効にするユーザー Office 365 の電話システムの設置の PSTN への接続を自分のドメインで、SIP アドレスがあります。 Office 365 の既定のドメイン onmicrosoft.com を使用することはサポートされていません。 

Office 365 のライセンスや計画などの電話システムに関する詳細については、 [Skype をビジネスのための計画の PSTN の呼び出し](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)を参照してください。

## <a name="feature-comparison"></a>機能比較

クラウド PBX を設置した PSTN 接続では、完全に、オンプレミス エンタープライズ VoIP ソリューションと同じ機能を提供していません。 クラウド PBX を設置した PSTN 接続が右に、組織の設定機能を提供するかどうかを決定するために、[ここではクラウド PBX との取得](https://go.microsoft.com/fwlink/?LinkId=715517)を参照してください。

## <a name="benefits-and-planning-considerations"></a>利点とプランニングの考慮事項

> [!CAUTION]
> オンプレミス環境で Skype for Business Online に移動する前に、Lync Phone Edition デバイスを最小要求ファームウェアに更新する必要があります。
オンプレミスからオンラインにユーザーを移動してからファームウェアを更新すると、ユーザーは電話を使用して接続できなくなります。 この問題を訂正するには、ユーザーをオンプレミス環境に戻して、電話を最小ファームウェアに更新する必要があります。 最小ファームウェアに更新するか、電話をハード リセットしてから、ユーザーをオンプレミス環境に戻すことは試みないでください。
デバイスが最小ファームウェアになっていないときにハード リセットを実行すると、既定で PIN 認証を使用するようになります。これは、Skype for Business Online でサポートされていません。 詳細については、[オンライン ビジネスの Skype の電話を取得](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。

Office 365 の電話システムを設置した PSTN 接続に配布すると、ユーザーを移動できます、クラウドに移行する Skype 経由でオンライン ビジネスの独自のペースでは、その設置した PSTN 接続を維持しながら。 PBX がある場合は、PBX を引き続き使用して、クラウドに移動するユーザーに PSTN 接続を提供します。 ビジネス オンラインと Office 365 の電話システムに Skype ユーザーを移動すると、従来の PBX 電話は動作しなくなりますがの電話番号にルーティング、Skype のいずれかのビジネス クライアント用の Pc やスマート フォンだけでなく、Skype の準拠のビジネス デスクの電話番号のs。 移植すると後で Office 365 のユーザーと従来の PBX のユーザーの電話システムことができます通常互いを呼び出すし、PSTN の呼び出しが通常の電話番号を使用して作成されます。

カスタム機能や、コール センターのような従来の PBX への主要なアドオンが備わっていることがあります。 カスタム機能が Office 365 の電話システムで現在利用可能ないない場合は、そのカスタム機能の設置型レガシ PBX は、単なるポートと Office 365 の電話システムにカスタム機能にアクセスする必要はありませんユーザーを必要とするそれらのユーザーをおく必要があります。設置 PSTN 接続します。

ビジネス サーバー 2015 の Skype を直接と互換性がある従来の Pbx の一覧については、 [Microsoft Lync のインフラストラクチャの修飾](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)を参照してください。 ユーザーの PBX がこの一覧にない場合は、オンライン ビジネスの Skype で Office 365 の電話システムとユーザーの PBX に接続するセッション ボーダー コント ローラーを使用できます。

### <a name="network-considerations-for-quality-and-performance"></a>ネットワークの品質とパフォーマンスに関する考慮事項

設置 PSTN への接続と Office 365 の電話システムのようなクラウドでホストされているサービスを展開すると、次を点に注意する必要があります。 純粋なオンプレミス Skype ビジネス サーバー 2015 のエンタープライズ VoIP の展開には、すべてのインフラストラクチャとクライアントは、企業のネットワークには。 このネットワークの品質とパフォーマンスは、高品質のオーディオとビデオにとって重要であり、エンタープライズのスタッフが直接制御することになります。 設置した PSTN 接続を Office 365 で、電話システムとは、関連する 3 つのネットワーク、2 つの顧客を担当するのですが、どの企業のスタッフは、直接を制御の 1 つだけがあります。

- **マイクロソフトのグローバル ・ メディア ・ サービス ・ ネットワーク**マイクロソフトのグローバルなクラウド ネットワークとインフラストラクチャです。 Office 365 および Office 365 のサーバーとトラフィックの電話システムは、このネットワークを通過します。

- **エンタープライズ/クラウドの PSTN の相互接続**これは、Office 365 のクラウドを導入する企業を接続するネットワークです。 これは必ずしも一般的なインターネット接続と同じです。

- **企業のネットワーク**リアルタイム メディアの品質は、独自のネットワークに大きく依存します。 特に、WiFi ネットワークと Office 365 のクラウドに到達するための相互接続の品質です。

> [!NOTE]
> Skype でのオンライン ビジネスのパフォーマンスのチューニングの詳細については、[オンライン ビジネスのパフォーマンスのための Skype のチューニング](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>設置 PSTN への接続での Office 365 の電話システムを使用するための前提条件

PSTN への接続を設置し、Skype をユーザーの移動と Office 365 の電話システムを構成するにはオンライン ビジネスを前に場所に次の前提条件があることを確認する必要があります。

 **設置型サーバーのバージョンです。** 設置型展開内のサーバーのバージョンは、Office 365 の電話システムを設置した PSTN 接続をサポートするのには次の表に記載されている必要があります。


| **サーバーの役割**                                       | **サポートされているバージョン\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| フェデレーション エッジ\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 次のホップ フェデレーション ルート内部プール サーバー  <br/> | Skype for Business Server 2015、2016 年 3 月の累積更新プログラム 6.0.9319.235 以降 (フロント エンドまたはディレクター)   <br/> |
| フロントエンド ユーザー サーバー  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| エッジ サーバー  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 仲介サーバー  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*最小のサポートされているバージョンは次のとおりです。

- Skype for Business Server 2015、2016 年 3 月の累積更新プログラム 6.0.9319.235

- Lync Server 2013、2015 年 7 月の累積更新プログラム 5.0.8308.920

\*\*ビジネス 2015 エッジ サーバーの実行中に Skype を経由してルーティングする必要がありますサポートされているすべての SIP ドメインのフェデレーションをルーティング以上 2016 年 3 月累計を更新します。 ユーザー プールが Lync Server 2013 にある場合、外部のプール トラフィックは Lync Server 2013 エッジ サーバー上に残ります。 

さらに次の操作を行う必要があります。

- **オンプレミス エンタープライズ VoIP が構成されオンプレミス ユーザーのテスト**これには、PSTN 接続コンポーネントが含まれます。 詳細については、 [Skype のビジネス サーバー 2015 でエンタープライズ VoIP の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)および[ビジネス サーバー 2015 の Skype でのエンタープライズ VoIP の展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)を参照してくださいビジネス サーバー 2015 の Skype を使用している場合は、次のトピックを参照してください。

    Lync Server 2013 を使用する場合は、 [Lync Server 2013 でエンタープライズ VoIP の計画](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)および[Lync Server 2013 でエンタープライズ VoIP を展開する](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)を参照してください。

- **Active Directory の同期**Azure AD 接続を使用して Active Directory の同期を構成する必要があります。 詳細については、 [Azure を管理する AD の接続](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)を参照してください。

    > [!NOTE]
    > 使用する AAD Connect のパーションは、バージョン 1.0.9125.0 以降である必要があります。それよりも前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。現在のインストールをアップグレードして、環境で定義しているカスタム ルールを維持できます。 

- **ハイブリッド展開を構成します。** かどうか、Skype をビジネス ユーザーには、現在すべてホームか、オンラインまたは設置型、またはある場合は現在、ミックス、[展開のハイブリッドで説明されているビジネス サーバーまたは Lync Server 2013 では、Skype のハイブリッド展開を構成する手順を完了する必要がありますSkype ビジネス サーバーと Office 365 間の接続](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。 ハイブリッド展開での詳細の背景については、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)を参照してください。 

    Lync Server 2013 を使用する場合は、 [Lync Server 2013 ハイブリッド](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)を参照してください。

- **Active Directory フェデレーション サービス (AD FS) (推奨)** シングル サインオンをサポートするために AD FS を展開することをお勧めします。 詳細については、 [Active Directory フェデレーション サービス (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)を参照してください。

Office 365 の電話システムを展開する方法の詳細については、[組織内の電話システムの設定](https://docs.microsoft.com/en-us/microsoftteams/setting-up-your-phone-system?toc=/skypeforbusiness/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)を参照してください。


