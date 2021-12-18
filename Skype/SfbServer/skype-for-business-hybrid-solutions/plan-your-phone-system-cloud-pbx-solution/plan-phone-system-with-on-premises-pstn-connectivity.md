---
title: Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムを計画する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: オンプレミス PSTN 接続を使用電話システム (Cloud PBX) の計画に関する考慮事項について説明します。
ms.openlocfilehash: a3c01ed32cb2654ea10773f53c4148262e3ee6c5
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562779"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムを計画する

> [!Important]
> Skype for Business 2021 年 7 月 31 日にオンラインが廃止され、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](/MicrosoftTeams/direct-routing-landing-page)。

オンプレミス PSTN 接続を使用電話システム (Cloud PBX) の計画に関する考慮事項について説明します。

このコンテンツは、オンプレミスで既にSkype for Business Server Lync Server 2013 が展開されている場合に関連します。 その他のシナリオについては [、「Microsoft テレフォニー ソリューション」を参照してください](/microsoftteams/cloud-voice-landing-page)。

 電話システム PSTN 接続を使用すると、ユーザーに電話システム (Cloud PBX) 機能を利用できます。 これは、次のシナリオに役立ちます。

- 一部のユーザー Skype for Businessオンプレミスに、その他のユーザーはオンラインSkype for Businessがあります。 Skype for Business Online に電話システム機能と機能を有効にできますが、引き続きオンプレミス PSTN 接続を使用できます。

- オンプレミス展開を使用し、一部またはすべてのユーザーを Skype for Business Online に移動しますが、引き続きオンプレミス PSTN 接続を使用します。

    > [!IMPORTANT]
    > オンプレミス PSTN 接続を使用してユーザー電話システムを正常に有効にするには、SIP アドレスが自分のドメインにある必要があります。 既定のドメインの使用は、Microsoft 365またはOffice 365 onmicrosoft.com サポートされていません。 

ライセンスとプランを含む電話システムの詳細については、「PSTN 通話プラン for Skype for Business」[を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>機能の比較

オンプレミス PSTN Connectivity を使用するクラウド PBX では、完全にオンプレミスのネットワーク ソリューションと同じ機能セットエンタープライズ VoIPではありません。 オンプレミス PSTN Connectivity を備え、クラウド PBX が組織に適切な機能セットを提供するかどうかを決定する方法については、「クラウド PBX を使用して得る情報を次に示します」を [参照してください](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)。

## <a name="benefits-and-planning-considerations"></a>利点と計画に関する考慮事項

> [!CAUTION]
> Lync 電話 Edition デバイスは、オンラインに移行する前に、オンプレミス環境で最低限必要なファームウェアSkype for Business必要です。
ファームウェアを更新する前にユーザーをオンプレミスからオンラインに移動すると、ユーザーは自分の携帯電話を使用して接続できません。 この問題を解決するには、電話を最小ファームウェアに更新するには、ユーザーをオンプレミス環境に戻す必要があります。 ユーザーをオンプレミス環境に戻す前に、最小限のファームウェアに更新したり、電話をハード リセットしたりしようとは行なって下さい。
デバイスが最小ファームウェアではない間にハード リセットが実行された場合、既定では PIN 認証が使用されます。これはオンラインではSkype for Businessされません。 詳細については[、「Getting phones for Skype for Businessオンライン」を参照してください](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

オンプレミス PSTN 接続電話システムを使用して展開することで、オンプレミスの PSTN 接続を維持しながら、Skype for Business Online 経由でユーザーを自分のペースでクラウドに移動できます。 PBX を使用している場合は、引き続き使用して、クラウドに移動するユーザーに PSTN 接続を提供します。 ユーザーが Skype for Business Online および 電話システム に移動すると、従来の PBX 電話は機能しなくなりましたが、その電話番号は PC またはスマートフォン用の Skype for Business クライアント、および Skype for Business 準拠のデスクフォンにルーティングされます。 移植が完了すると電話システム PBX ユーザーは、通常の電話番号を使用して PSTN 通話を発信/受信できます。

カスタム機能や、通話センターなどの従来の PBX の主要なアドオンがある場合があります。 電話システム で現在カスタム機能を使用できない場合は、そのカスタム機能を必要とするユーザーを従来の PBX に残し、カスタム機能にアクセスする必要がないユーザーをオンプレミス PSTN 接続で 電話システム に移植する必要があります。

Skype for Business Server 2015 年 2015 年と直接相互運用する従来の PBX の一覧については[、「Infrastructure qualified for Microsoft Lync」を参照してください](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 PBX がこの一覧に表示されていない場合は、セッション ボーダー コントローラーを使用して、PBX をオンラインで電話システム接続Skype for Businessできます。

### <a name="network-considerations-for-quality-and-performance"></a>品質とパフォーマンスに関するネットワークに関する考慮事項

オンプレミス PSTN 接続を使用してクラウドホスト型電話システムサービスを展開する場合は、以下を念頭に置く必要があります。 2015 年の完全なオンプレミスSkype for Business Server展開エンタープライズ VoIP、すべてのインフラストラクチャとクライアントが企業の独自のネットワーク上に配置されています。 高品質のオーディオとビデオにとって重要なこのネットワークの品質とパフォーマンスは、企業のスタッフが直接制御します。 オンプレミス電話システム PSTN 接続を使用すると、3 つのネットワークが関係し、そのうち 2 つは顧客が担当しますが、エンタープライズ スタッフが直接制御できるのは 1 つのみです。

- **Microsoft のグローバル メディア配信ネットワーク** Microsoft のグローバル クラウド ネットワークとインフラストラクチャ。 電話システムトラフィックは、このネットワークを通過します。

- **Enterprise/クラウド PSTN インターコネクト** これは、企業をクラウドに接続するネットワークです。 これは、必ずしも一般的なインターネット接続と同じではありません。

- **エンタープライズ独自のネットワーク** リアルタイム メディアの品質は、独自のネットワーク、特に WiFi ネットワーク、およびクラウドに到達するために使用される相互接続の品質に大きく依存します。

> [!NOTE]
> オンラインでのパフォーマンスの調整の詳細については、「Skype for Businessのパフォーマンスの調整[」をSkype for Businessしてください](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミス PSTN 接続電話システムを使用するための前提条件

オンプレミス PSTN 接続を使用電話システムを構成し、ユーザーを Skype for Business Online に移動する前に、次の前提条件が満たされていることを確認する必要があります。

 **オンプレミス サーバーのバージョン。** オンプレミスの PSTN 接続をサポートするには、オンプレミス展開のサーバーのバージョンを次電話システムする必要があります。


| **サーバーの役割**                                       | **サポートされているバージョン\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| フェデレーション エッジ\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Next Hop フェデレーション ルートの内部プール サーバー  <br/> | Skype for Business Server 2015 年 3 月累積的な更新プログラム 6.0.9319.235 以上 (フロントエンドまたはディレクター)  <br/> |
| フロントエンド ユーザー サーバー  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| エッジ サーバー  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 仲介サーバー  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*サポートされている最小バージョンは次のとおりです。

- Skype for Business Server 2015 年 3 月累積的な更新プログラム 6.0.9319.235

- Lync Server 2013 2015 年 7 月累積的な更新プログラム 5.0.8308.920

\*\*サポートされているすべての SIP ドメインのフェデレーション ルートは、2016 年 3 月以上の累積的な更新プログラムを実行Skype for Business Server 2015 エッジ サーバーを経由してルーティングする必要があります。 ユーザー プールが Lync Server 2013 上にある場合、その外部プール トラフィックは Lync Server 2013 エッジ サーバーに残ります。 

さらに、次の情報を確認する必要があります。

- **オンプレミス のユーザーエンタープライズ VoIP構成** され、テストされます。これには、PSTN 接続コンポーネントが含まれます。 詳細については、Skype for Business Server 2015 を使用している場合は、次のトピックを参照してください。「エンタープライズ VoIP 2015 の計画」および「Skype for Business Server [2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)でのエンタープライズ VoIPの展開」を[参照してください。Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Lync Server 2013 を使用している場合は[、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice)での エンタープライズ VoIP の計画」および「Lync Server [2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)での エンタープライズ VoIPの展開」を参照してください。

- **Active Directory の同期** Active Directory 同期を構成するには、次の手順を使用Azure AD Connect。 詳細については、「Azure AD Connect」[を参照してください](/azure/active-directory/hybrid/how-to-connect-install-custom)。

    > [!NOTE]
    > 使用するAAD Connectバージョンはバージョン 1.0.9125.0 以降である必要があります。 以前のバージョンのツールまたは DirSync をAAD Connect場合は、サポートされているバージョンにアップグレードしてください。 現在のインストールをアップグレードし、環境で定義したカスタム ルールを維持できます。 

- **ハイブリッド展開を構成する** すべての Skype for Business ユーザーが現在オンラインまたはオンプレミスのどちらに配置されているのか、または現在混在している場合は、「ハイブリッド接続を間に展開する」で説明されている Skype for Business Server または Lync Server 2013 のハイブリッド展開を構成する手順を完了する必要があります。 [Skype for Business ServerとOffice 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。 ハイブリッド展開の背景の詳細については、「ハイブリッド接続を計画する」を参照[Skype for Business Serverと](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)Office 365。 

    Lync Server 2013 を使用している場合は [、「Lync Server 2013 ハイブリッド」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)。

- **(推奨)Active Directory フェデレーション サービス (AD FS)。** シングル サインオンをサポートAD FS を展開することをお勧めします。 詳細については [、「Active Directory フェデレーション サービス (AD FS)」を参照してください](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))。

展開の詳細については、「電話システムでオンプレミス PSTN 接続電話システムユーザーを有効にする」を[参照Skype for Business Server。](enable-users-for-phone-system.md)
