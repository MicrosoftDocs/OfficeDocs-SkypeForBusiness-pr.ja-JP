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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: オンプレミス PSTN 接続を使用した電話システム (クラウド PBX) の計画に関する考慮事項について説明します。
ms.openlocfilehash: afa97a00b474017e6aed5e92802e7ba13483f7af
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064703"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムを計画する

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

オンプレミス PSTN 接続を使用した電話システム (クラウド PBX) の計画に関する考慮事項について説明します。

このコンテンツは、Skype for Business Server または Lync Server 2013 がオンプレミスで展開済みの場合に関連します。 その他のシナリオについては [、「Microsoft テレフォニー ソリューション」を参照してください](/microsoftteams/cloud-voice-landing-page)。

 オンプレミスの PSTN 接続を使用した電話システムを使用すると、ユーザーに電話システム (Cloud PBX) 機能を利用できます。 これは、次のシナリオに役立ちます。

- 一部の Skype for Business ユーザーはオンプレミスに、他のユーザーは Skype for Business Online に保存されています。 これで、Skype for Business Online に登録されているユーザーに対して電話システムの機能と機能を有効にできますが、引き続きオンプレミス PSTN 接続を使用できます。

- オンプレミス展開を使用し、ユーザーの一部またはすべてのユーザーを Skype for Business Online に移動しますが、引き続きオンプレミス PSTN 接続を使用します。

    > [!IMPORTANT]
    > オンプレミスの PSTN 接続を使用して電話システムのユーザーを正常に有効にするには、SIP アドレスが自分のドメインにある必要があります。 Microsoft 365 または microsoft 365 または Office 365 onmicrosoft.com の使用はサポートされていません。 

ライセンスとプランを含む電話システムの詳細については [、「SKYPE for Business の PSTN 通話プラン」を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>機能の比較

オンプレミス PSTN Connectivity を使用するクラウド PBX では、完全にオンプレミスのネットワーク ソリューションと同じ機能セットエンタープライズ VoIPではありません。 オンプレミス PSTN Connectivity を備え、クラウド PBX が組織に適切な機能セットを提供するかどうかを決定する方法については、「クラウド PBX を使用して得る情報を次に示します」を [参照してください](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)。

## <a name="benefits-and-planning-considerations"></a>利点と計画に関する考慮事項

> [!CAUTION]
> Lync Phone Edition デバイスは、Skype for Business Online に移行する前に、オンプレミス環境で最低限必要なファームウェアに更新する必要があります。
ファームウェアを更新する前にユーザーをオンプレミスからオンラインに移動すると、ユーザーは自分の携帯電話を使用して接続できません。 この問題を解決するには、電話を最小ファームウェアに更新するには、ユーザーをオンプレミス環境に戻す必要があります。 ユーザーをオンプレミス環境に戻す前に、最小限のファームウェアに更新したり、電話をハード リセットしたりしようとは行なって下さい。
デバイスが最小ファームウェアではない間にハード リセットが実行された場合、既定では PIN 認証が使用されます。これは Skype for Business Online ではサポートされていません。 詳細については [、「Getting phones for Skype for Business Online」を参照してください](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

オンプレミスの PSTN 接続を使用して電話システムを展開することで、オンプレミスの PSTN 接続を維持しながら、Skype for Business Online を介してユーザーを自分のペースでクラウドに移動できます。 PBX を使用している場合は、引き続き使用して、クラウドに移動するユーザーに PSTN 接続を提供します。 ユーザーが Skype for Business Online および電話システムに移動すると、従来の PBX 電話は機能しなくなりましたが、その電話番号は、PC またはスマートフォン用の Skype for Business クライアント、および Skype for Business 準拠のデスクフォンにルーティングされます。 移植が完了すると、電話システム ユーザーと従来の PBX ユーザーは、通常の電話番号を使用して PSTN 通話を発信または受信できます。

カスタム機能や、通話センターなどの従来の PBX の主要なアドオンがある場合があります。 カスタム機能が電話システムで現在使用できない場合は、そのカスタム機能を必要とするユーザーを従来の PBX にそのままにし、カスタム機能にアクセスする必要はないユーザーをオンプレミスの PSTN 接続で電話システムに移植する必要があります。

Skype for Business Server 2015 と直接相互運用する従来の PBX の一覧については、「Microsoft Lync のインフラストラクチャ  [認定」を参照してください](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 PBX がこのリストに含されていない場合は、セッション ボーダー コントローラーを使用して、Skype for Business Online の電話システムに PBX を接続できます。

### <a name="network-considerations-for-quality-and-performance"></a>品質とパフォーマンスに関するネットワークに関する考慮事項

オンプレミスの PSTN 接続を使用して電話システムのようなクラウドホスト型サービスを展開する場合は、次の情報を念頭に置く必要があります。 完全にオンプレミスの Skype for Business Server 2015 エンタープライズ VoIP展開では、すべてのインフラストラクチャとクライアントが企業の独自のネットワーク上に配置されます。 高品質のオーディオとビデオにとって重要なこのネットワークの品質とパフォーマンスは、企業のスタッフが直接制御します。 オンプレミスの PSTN 接続を備える電話システムでは、3 つのネットワークが関係し、そのうち 2 つは顧客が担当しますが、エンタープライズ スタッフが直接制御できるのは 1 つのみです。

- **Microsoft のグローバル メディア配信ネットワーク** Microsoft のグローバル クラウド ネットワークとインフラストラクチャ。 電話システム サーバーとトラフィックは、このネットワークを通過します。

- **エンタープライズ/クラウド PSTN インターコネクト** これは、企業をクラウドに接続するネットワークです。 これは、必ずしも一般的なインターネット接続と同じではありません。

- **エンタープライズ独自のネットワーク** リアルタイム メディアの品質は、独自のネットワーク、特に WiFi ネットワーク、およびクラウドに到達するために使用される相互接続の品質に大きく依存します。

> [!NOTE]
> Skype for Business Online でのパフォーマンスのチューニングの詳細については、「Tune Skype for Business Online performance [」を参照してください](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>オンプレミス PSTN 接続で電話システムを使用するための前提条件

オンプレミスの PSTN 接続を使用して電話システムを構成し、ユーザーを Skype for Business Online に移動する前に、次の前提条件が満たされていることを確認する必要があります。

 **オンプレミス サーバーのバージョン。** オンプレミスの PSTN 接続を使用して電話システムをサポートするには、オンプレミス展開内のサーバーのバージョンを次の表に示す必要があります。


| **サーバーの役割**                                       | **サポートされているバージョン\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| フェデレーション エッジ\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Next Hop フェデレーション ルートの内部プール サーバー  <br/> | Skype for Business Server 2015、2016 年 3 月累積的な更新プログラム 6.0.9319.235 以上 (フロントエンドまたはディレクター)  <br/> |
| フロントエンド ユーザー サーバー  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| エッジ サーバー  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 仲介サーバー  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*サポートされている最小バージョンは次のとおりです。

- Skype for Business Server 2015、2016 年 3 月累積的な更新プログラム 6.0.9319.235

- Lync Server 2013 2015 年 7 月累積的な更新プログラム 5.0.8308.920

\*\*サポートされているすべての SIP ドメインのフェデレーション ルートは、2016 年 3 月以上の累積的な更新プログラムを実行している Skype for Business Server 2015 エッジ サーバーを経由する必要があります。 ユーザー プールが Lync Server 2013 上にある場合、その外部プール トラフィックは Lync Server 2013 エッジ サーバーに残ります。 

さらに、次の情報を確認する必要があります。

- **オンプレミス のユーザーエンタープライズ VoIPの構成とテストを** 行うオンプレミス のユーザー向けこれには、PSTN 接続コンポーネントが含まれます。 詳細については、Skype for Business Server 2015 を使用している場合は、次のトピックを参照してください。「Plan for エンタープライズ VoIP in [Skype for Business Server 2015」](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) および「Deploy エンタープライズ VoIP in Skype for Business Server [2015」](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)を参照してください。

    Lync Server 2013 を使用している場合は [、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) での エンタープライズ VoIP の計画」および「Lync Server [2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)での エンタープライズ VoIPの展開」を参照してください。

- **Active Directory の同期** Azure サーバー接続を使用して Active Directory 同期を構成ADがあります。 詳細については [、「Managing Azure AD接続」を参照してください](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 使用する AAD Connect のバージョンは、バージョン 1.0.9125.0 以降である必要があります。 以前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。 現在のインストールをアップグレードし、環境で定義したカスタム ルールを維持できます。 

- **ハイブリッド展開を構成する** すべての Skype for Business ユーザーが現在オンラインまたはオンプレミスのどちらに配置されている場合でも、現在混在している場合は、「Skype for Business Server と [Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)とのハイブリッド接続の展開」で説明されている手順を完了して、Skype for Business Server または Lync Server 2013 のハイブリッド展開を構成する必要があります。 ハイブリッド展開の背景の詳細については、「Plan hybrid connectivity between [Skype for Business Server and Office 365」を参照してください](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。 

    Lync Server 2013 を使用している場合は [、「Lync Server 2013 ハイブリッド」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)。

- **(推奨)Active Directory フェデレーション サービス (AD FS)。** シングル サインオンをサポートAD FS を展開することをお勧めします。 詳細については [、「Active Directory フェデレーション サービス (AD FS)」を参照してください](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))。

電話システムの展開の詳細については、「Enable users for Phone System with オンプレミス [PSTN connectivity in Skype for Business Server」を参照してください](enable-users-for-phone-system.md)。