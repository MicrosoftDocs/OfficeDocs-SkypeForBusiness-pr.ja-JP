---
title: Skype for Business Server でオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを計画する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
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
description: オンプレミスの PSTN 接続を使用した、Office 365 (クラウド PBX) での電話システムの計画に関する考慮事項について説明します。
ms.openlocfilehash: 1ca12d1680b56612c2e6f3a1785ee615138294ce
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221044"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを計画する

オンプレミスの PSTN 接続を使用した、Office 365 (クラウド PBX) での電話システムの計画に関する考慮事項について説明します。

このコンテンツは、オンプレミスの Skype for Business Server または Lync Server 2013 を既に展開している場合に該当します。 その他のシナリオについては、「 [Microsoft telephony ソリューション](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)」を参照してください。

 オンプレミスの PSTN 接続を使用した Office 365 の電話システムでは、ユーザーに対して電話システム (クラウド PBX) 機能を活用することができます。 これは、次のようなシナリオで役立ちます。

- Skype for Business の一部のユーザーがオンプレミスで、Skype for Business Online をホームにしている場合。 Office 365 の機能と、Skype for Business Online に接続されたユーザーのために、電話システムを有効にできるようになりましたが、オンプレミスの PSTN 接続は引き続き使用できます。

- オンプレミスの展開を行っていて、一部またはすべてのユーザーを Skype for Business Online に移行する必要があるが、オンプレミスの PSTN 接続を引き続き使用する場合。

    > [!IMPORTANT]
    > オンプレミスの PSTN 接続を使用して、Office 365 で電話システムのユーザーを正常に有効にするには、その SIP アドレスが自分のドメインにある必要があります。 Office 365 の既定のドメイン onmicrosoft.com を使用することはサポートされていません。 

ライセンスやプランなど、Office 365 の電話システムの詳細については、「 [Skype For business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。

## <a name="feature-comparison"></a>機能比較

オンプレミスの PSTN 接続を使用したクラウド PBX では、完全なオンプレミスのエンタープライズボイスソリューションと同じ機能セットが提供されません。 オンプレミスの PSTN 接続を使用したクラウド PBX が組織に適した機能セットを提供するかどうかを判断するために、[クラウド pbx で利用](https://go.microsoft.com/fwlink/?LinkId=715517)できる機能を紹介します。

## <a name="benefits-and-planning-considerations"></a>利点とプランニングの考慮事項

> [!CAUTION]
> オンプレミス環境で Skype for Business Online に移動する前に、Lync Phone Edition デバイスを最小要求ファームウェアに更新する必要があります。
オンプレミスからオンラインにユーザーを移動してからファームウェアを更新すると、ユーザーは電話を使用して接続できなくなります。 この問題を訂正するには、ユーザーをオンプレミス環境に戻して、電話を最小ファームウェアに更新する必要があります。 最小ファームウェアに更新するか、電話をハード リセットしてから、ユーザーをオンプレミス環境に戻すことは試みないでください。
デバイスが最小ファームウェアになっていないときにハード リセットを実行すると、既定で PIN 認証を使用するようになります。これは、Skype for Business Online でサポートされていません。 詳細については、「 [Skype For Business Online の電話を取得](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)する」を参照してください。

オンプレミスの PSTN 接続を使用して Office 365 に電話システムを展開することで、オンプレミスの PSTN 接続を維持したまま、自分のペースで Skype for Business Online を使って、ユーザーをクラウドに移行することができます。 PBX がある場合は、PBX を引き続き使用して、クラウドに移動するユーザーに PSTN 接続を提供します。 ユーザーが Office 365 の Skype for Business Online および電話システムに移動されると、その従来の PBX 電話は機能しなくなりますが、携帯電話番号は、Pc またはスマートフォン用の Skype for Business クライアント、および Skype for Business 対応の卓上電話のいずれかにルーティングされます。レ 移植後、Office 365 ユーザーおよび従来の PBX ユーザーの電話システムは、通常の電話番号を使用して PSTN 通話の発信と受信を行うことができるようになります。

カスタム機能や、コール センターのような従来の PBX への主要なアドオンが備わっていることがあります。 カスタム機能が Office 365 の電話システムで現在利用できない場合は、そのカスタム機能を必要としているユーザーを従来の PBX と共にオンプレミスのままにして、カスタム機能にアクセスする必要のないユーザーを Office 365 の電話システムに移植する必要があります。オンプレミスの PSTN 接続を使用します。

Skype for Business Server 2015 で直接相互運用できる従来の Pbx のリストについては、「 [Microsoft Lync 用のインフラストラクチャ認定](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)」をご覧ください。 お使いの PBX がこの一覧にない場合は、セッション境界コントローラーを使用して、Skype for Business Online の Office 365 で PBX を電話システムに接続することができます。

### <a name="network-considerations-for-quality-and-performance"></a>ネットワークの品質とパフォーマンスに関する考慮事項

電話システムなどのクラウドホスト型サービスを、オンプレミスの PSTN 接続を使用して Office 365 に展開する場合は、次の点に注意する必要があります。 純粋なオンプレミスの Skype for Business Server 2015 エンタープライズ Voip の展開では、すべてのインフラストラクチャとクライアントが企業独自のネットワーク上にあります。 このネットワークの品質とパフォーマンスは、高品質のオーディオとビデオにとって重要であり、エンタープライズのスタッフが直接制御することになります。 オンプレミスの PSTN 接続を使用した Office 365 の電話システムでは、次の2つのネットワークが関係していますが、そのうちの2つはエンタープライズスタッフが直接管理しているネットワークです。

- **Microsoft のグローバルメディア配信ネットワーク**Microsoft のグローバルクラウドネットワークとインフラストラクチャ。 Office 365 および電話システムの Office 365 サーバーとトラフィックは、このネットワークをスキャンします。

- **Enterprise/CLOUD PSTN 相互接続**エンタープライズを Office 365 クラウドに接続するネットワークです。 これは、一般的なインターネット接続と同じであるとは限りません。

- **企業の独自のネットワーク**リアルタイムメディアの品質は、独自のネットワーク (特に WiFi ネットワークと、Office 365 クラウドに接続するために使用される相互接続の品質) に大きく依存しています。

> [!NOTE]
> Skype for Business Online のパフォーマンスの調整の詳細については、「 [skype for Business online のパフォーマンスのチューニング](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>オンプレミスの PSTN 接続を使用して、Office 365 で電話システムを使用するための前提条件

オンプレミスの PSTN 接続を使用して Office 365 で電話システムを構成し、ユーザーを Skype for Business Online に移行するには、次の前提条件が満たされていることを確認する必要があります。

 **オンプレミスサーバーのバージョン。** オンプレミスの PSTN 接続を使用して Office 365 の電話システムをサポートするには、オンプレミスの展開に含まれているサーバーのバージョンが、次の表に記載されている必要があります。


| **サーバーの役割**                                       | **サポートされているバージョン\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| フェデレーションエッジ\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 次のホップ フェデレーション ルート内部プール サーバー  <br/> | Skype for Business Server 2015、2016 年 3 月の累積更新プログラム 6.0.9319.235 以降 (フロント エンドまたはディレクター)   <br/> |
| フロントエンド ユーザー サーバー  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| エッジ サーバー  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 仲介サーバー  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*サポートされている最小バージョン:

- Skype for Business Server 2015、2016 年 3 月の累積更新プログラム 6.0.9319.235

- Lync Server 2013、2015 年 7 月の累積更新プログラム 5.0.8308.920

\*\*サポートされているすべての SIP ドメインのフェデレーションルートは、2016年3月以降の累積更新プログラムを実行している Skype for Business Server 2015 エッジサーバーを経由してルーティングする必要があります。 ユーザー プールが Lync Server 2013 にある場合、外部のプール トラフィックは Lync Server 2013 エッジ サーバー上に残ります。 

さらに、次のことを確認する必要があります。

- オンプレミス**のエンタープライズ voip がオンプレミスユーザー向けに構成されテストされ**ているこれには PSTN 接続コンポーネントが含まれます。 詳細については、「skype for business server 2015 を使用している場合は、次のトピックを参照してください。 skype for business server [2015 でのエンタープライズ voip の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)」および「 [Skype for business server 2015 でのエンタープライズボイスの展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)」を参照してください。

    Lync Server 2013 を使っている場合は、「lync server [2013 でのエンタープライズ voip の計画](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)」および「 [lync server 2013 でのエンタープライズ voip の展開](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)」をご覧ください。

- **Active Directory の同期**Azure AD Connect を使用して Active Directory の同期を構成する必要があります。 詳細については、「 [AZURE AD Connect を管理する](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)」を参照してください。

    > [!NOTE]
    > 使用する AAD Connect のパーションは、バージョン 1.0.9125.0 以降である必要があります。それよりも前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。現在のインストールをアップグレードして、環境で定義しているカスタム ルールを維持できます。 

- **ハイブリッド展開を構成する**すべての Skype for Business ユーザーが現在、オンラインまたはオンプレミスのいずれかであるか。または、現在混在している場合は、「ハイブリッド展開」で説明されているように、Skype for Business Server または Lync Server 2013 のハイブリッド展開を構成するための手順を完了する必要があります。 [Skype for Business Server と Office 365 間の接続](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。 ハイブリッド展開の詳細については、「 [Skype For Business Server と Office 365 の間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」を参照してください。 

    Lync Server 2013 を使っている場合は、「 [Lync server 2013 ハイブリッド](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)」を参照してください。

- **勧めActive Directory フェデレーションサービス (AD FS)。** シングルサインオンをサポートするには、AD FS を展開することをお勧めします。 詳細については、「 [Active Directory フェデレーションサービス (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)」を参照してください。

Office 365 での電話システムの展開の詳細については、「 [Skype For Business Server のオンプレミスの PSTN 接続を使用して、office 365 の電話システムでユーザーを有効にする](enable-users-for-phone-system.md)」を参照してください。


