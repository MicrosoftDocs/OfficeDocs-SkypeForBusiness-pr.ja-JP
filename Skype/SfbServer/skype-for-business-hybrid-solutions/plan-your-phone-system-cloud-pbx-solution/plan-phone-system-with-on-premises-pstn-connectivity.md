---
title: Skype for Business Server でオンプレミスの PSTN 接続を使用して Office 365 で電話システムを計画する
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
description: オンプレミスの PSTN 接続を備えた Office 365 (クラウド PBX) の電話システムの計画に関する考慮事項について説明します。
ms.openlocfilehash: be8fbe5671e2959341c08d4efa45829df0cc5e42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42020228"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server でオンプレミスの PSTN 接続を使用して Office 365 で電話システムを計画する

オンプレミスの PSTN 接続を備えた Office 365 (クラウド PBX) の電話システムの計画に関する考慮事項について説明します。

このコンテンツは、既に Skype for Business Server または Lync Server 2013 を社内で展開している場合に関連しています。 その他のシナリオについては、「 [Microsoft テレフォニーソリューション](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)」を参照してください。

 オンプレミスの PSTN 接続を備えた Office 365 の電話システムでは、ユーザーの電話システム (クラウド PBX) の機能を活用することができます。 これは、次のシナリオで役立ちます。

- 一部の Skype for Business ユーザーには、オンプレミスに所属し、Skype for Business Online に所属している他のユーザーがいます。 Office 365 の電話システムで、Skype for Business Online に所属しているユーザーの機能を有効にできますが、オンプレミスの PSTN 接続を引き続き使用することができます。

- オンプレミスの展開があり、一部またはすべてのユーザーを Skype for Business Online に移動する必要がありますが、オンプレミスの PSTN 接続を引き続き使用します。

    > [!IMPORTANT]
    > オンプレミスの PSTN 接続を備えた Office 365 の電話システムでユーザーを正常に有効にするには、その SIP アドレスが自分のドメイン内にある必要があります。 Office 365、onmicrosoft.com の既定のドメインの使用はサポートされていません。 

ライセンスとプランを含む Office 365 の電話システムの詳細については、「 [Skype For business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。

## <a name="feature-comparison"></a>機能の比較

オンプレミスの PSTN 接続を備えたクラウド PBX は、完全な社内エンタープライズ Voip ソリューションと同じ機能セットを提供しません。 オンプレミスの PSTN 接続を使用するクラウド PBX が組織に適切な機能セットを提供するかどうかを判断するには、[クラウド pbx で利用できるもの](https://go.microsoft.com/fwlink/?LinkId=715517)を参照してください。

## <a name="benefits-and-planning-considerations"></a>利点と計画に関する考慮事項

> [!CAUTION]
> Lync Phone Edition デバイスは、Skype for Business Online に移行する前に、オンプレミス環境で最低限必要なファームウェアに更新する必要があります。
ファームウェアを更新する前に、ユーザーをオンプレミスからオンラインに移動すると、ユーザーは電話を使用して接続できなくなります。 この問題を解決するには、ユーザーをオンプレミス環境に戻して、電話を最小ファームウェアに更新する必要があります。 ユーザーをオンプレミス環境に戻す前に、最小限のファームウェアに更新したり、電話をハードリセットしたりしないでください。
デバイスが最低限のファームウェアではない場合にハードリセットが実行されると、既定では、Skype for Business Online ではサポートされていない PIN 認証が使用されます。 詳細については、「 [Skype for Business Online の電話機の入手](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。

Office 365 で電話システムをオンプレミスの PSTN 接続と共に展開することで、オンプレミスの PSTN 接続を保持しながら、自分のペースで Skype for Business Online を使用してユーザーをクラウドに移行することができます。 PBX を所有している場合は、その PBX を使用して、クラウドに移動するユーザーに PSTN 接続を提供することができます。 Office 365 の Skype for Business Online および電話システムにユーザーを移動すると、その従来の PBX 電話は動作しなくなりますが、電話番号は、Pc またはスマートフォンの Skype for Business クライアントまたは Skype for Business に準拠した電話機のいずれかにルーティングされます。レ 移植後、Office 365 ユーザーと従来の PBX ユーザーは互いに通常どおりに通話でき、通常の電話番号を使用して PSTN 通話の発信と受信を行うことができます。

コールセンターなど、従来の PBX にカスタム機能または主要なアドオンがある場合があります。 カスタム機能が Office 365 の電話システムで現在利用できない場合は、そのカスタム機能を必要とするユーザーを従来の PBX でオンプレミスのままにしておく必要があります。また、カスタム機能にアクセスする必要のないユーザーを Office 365 の電話システムに移植する必要はありません。オンプレミスの PSTN 接続。

Skype for Business Server 2015 と直接相互運用する従来の Pbx の一覧については、「 [Microsoft Lync 用のインフラストラクチャ認定](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)」を参照してください。 PBX がこのリストに含まれていない場合は、セッションボーダーコントローラーを使用して、Skype for Business Online の Office 365 で PBX を電話システムに接続することができます。

### <a name="network-considerations-for-quality-and-performance"></a>ネットワークの品質とパフォーマンスに関する考慮事項

オンプレミスの PSTN 接続を備えた Office 365 で、電話システムのようなクラウドにホストされるサービスを展開する場合は、次の点を考慮する必要があります。 純粋なオンプレミスの Skype for Business Server 2015 エンタープライズ Voip の展開では、すべてのインフラストラクチャとクライアントが企業独自のネットワーク上に配置されています。 このネットワークの品質とパフォーマンスは、高品質のオーディオおよびビデオにとって重要であり、エンタープライズスタッフの直接的な制御下にあります。 Office 365 の電話システムでオンプレミスの PSTN 接続を使用する場合は、次の3つのネットワークが関係しています。そのうち2つは、お客様が責任を担い、そのうちの1つはエンタープライズスタッフが直接制御しています。

- **Microsoft のグローバルメディア配信ネットワーク**Microsoft のグローバルクラウドネットワークとインフラストラクチャ。 Office 365 と電話システムの Office 365 サーバーとトラフィックがこのネットワークをスキャンします。

- **エンタープライズ/クラウド PSTN 相互接続**これは、企業を Office 365 クラウドに接続するネットワークです。 これは、一般的なインターネット接続と同じであるとは限りません。

- **企業の独自のネットワーク**リアルタイムメディアの品質は、自分のネットワークに大きく依存しています。特に、WiFi ネットワークおよび Office 365 クラウドに到達するために使用される相互接続の品質です。

> [!NOTE]
> Skype for business Online でのパフォーマンスのチューニングの詳細については、「 [skype for Business online のパフォーマンス](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)をチューニングする」を参照してください。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>オンプレミスの PSTN 接続を備えた Office 365 で電話システムを使用するための前提条件

オンプレミスの PSTN 接続を使用して Office 365 で電話システムを構成し、ユーザーを Skype for Business Online に移動する前に、次の前提条件が満たされていることを確認する必要があります。

 **オンプレミスのサーバーバージョン。** オンプレミスの PSTN 接続を備えた Office 365 の電話システムをサポートするには、社内展開にあるサーバーのバージョンを次の表に示すようにします。


| サーバーの役割は、新しいファームを作成するとき、またはサーバーを既存のファームに参加させるときに指定します。                                       | **サポートされているバージョン\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| フェデレーションエッジ\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 次ホップフェデレーションルート内部プールサーバー  <br/> | Skype for Business Server 2015、2016年3月の累積的な更新プログラムプログラム6.0.9319.235 以降またはそれ以上 (フロントエンドまたはディレクター)  <br/> |
| フロントエンドユーザーサーバー  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| エッジ サーバー  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 仲介サーバー  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*サポートされている最小のバージョンは次のとおりです。

- Skype for Business Server 2015、2016年3月の累積更新プログラムプログラム6.0.9319.235 以降

- Lync Server 2013 年7月2015の累積的な更新プログラムの5.0.8308.920

\*\*サポートされているすべての SIP ドメインのフェデレーションルートは、2016年3月以降の累積更新プログラムを実行している Skype for Business Server 2015 エッジサーバーを経由してルーティングする必要があります。 ユーザープールが Lync Server 2013 上にある場合、その外部プールのトラフィックは Lync Server 2013 エッジサーバー上に残ります。 

さらに、次のことを確認する必要があります。

- オンプレミス**のエンタープライズ voip が、オンプレミスのユーザーに対して構成およびテストされ**ているこれには、PSTN 接続コンポーネントが含まれます。 詳細については、以下のトピックを参照してください。 Skype for business Server 2015 を使用している場合は、「 [Plan For Enterprise voice In skype For Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 」と「 [Deploy Enterprise voice In Skype for business server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)」を参照してください。

    Lync Server 2013 を使用している場合は、「 [Planning For Enterprise voice In Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) 」および「 [lync Server 2013 でエンタープライズ voip を展開](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx)する」を参照してください。

- **Active Directory の同期**Azure AD Connect を使用して Active Directory の同期を構成する必要があります。 詳細については、「 [AZURE AD Connect の管理](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)」を参照してください。

    > [!NOTE]
    > 使用する AAD Connect のバージョンは、バージョン1.0.9125.0 以降以降である必要があります。 以前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。 現在のインストールをアップグレードして、環境で定義したカスタムルールを維持することができます。 

- **ハイブリッド展開を構成する**すべての Skype for Business ユーザーが現在オンラインまたはオンプレミスに所属しているかどうか、または現在混在している場合は、skype for business [server と Office 365 の間のハイブリッド接続の展開](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)に関する説明に従って、Skype For business server または Lync Server 2013 のハイブリッド展開を構成する手順を完了する必要があります。 ハイブリッド展開の詳細については、「 [Skype For Business Server と Office 365 の間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)する」を参照してください。 

    Lync Server 2013 を使用している場合は、「 [Lync server 2013 hybrid](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)」を参照してください。

- **勧めActive Directory フェデレーションサービス (AD FS)。** シングルサインオンをサポートするには、AD FS を展開することをお勧めします。 詳細については、「 [Active Directory フェデレーションサービス (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx)」を参照してください。

Office 365 での電話システムの展開の詳細については、「 [Enable users For Phone system In office 365 with ON-PREMISES PSTN connectivity In Skype For Business Server](enable-users-for-phone-system.md)」を参照してください。


