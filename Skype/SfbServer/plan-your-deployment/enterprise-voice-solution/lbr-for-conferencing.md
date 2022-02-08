---
title: Location-Basedでの会議のルーティングSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: コンサルティング通話の転送を含む、Skype for Business Server エンタープライズ VoIP会議の場所ベースのルーティングを計画します。
ms.openlocfilehash: 3c5c7e4d374e9ece3ee0f0ce092d4030d2d84100
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387705"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Basedでの会議のルーティングSkype for Business Server

コンサルティング通話の転送を含む、Skype for Business Server エンタープライズ VoIP会議の場所ベースのルーティングを計画します。

Location-Basedルーティングを使用すると、通話内の関係者の場所に基づいて、VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを制限できます。 Location-Basedルーティングを使用すると、PSTN 通話料のバイパスを防止Location-Based会議 (会議) にルーティング ルールを適用できます。 アプリケーションはアクティブな会議を監視し、Location-Basedの場所に基づいてルーティング制限を適用します。 またLocation-Based会議用ルーティング アプリケーションを使用すると、PSTN エンドポイントを含むLocation-Basedに対するルーティング制限を適用できます。

ルーティングLocation-Basedアプリケーションは、PSTN 有料Skype for Business防止するためのメカニズムを電話会議に提供します。 アプリケーションは、アクティブな会議を監視し、Location-Basedユーザーの場所に基づいてルーティングの制限Skype for Business適用します。

[Location-Basedルーティング会議アプリケーションは、次Location-Based条件が満たされている場合、Skype for Business会議にルーティングを適用するかどうかを決定します。

- 会議の開催者は、ルーティングのLocation-Basedされます。 Location-Basedルーティング制限は、ルーティングを有効にしているユーザーが組織する会議にのみLocation-Basedされます。

- 少なくとも 1 人の会議参加者が PSTN エンドポイントです。 Location-Basedルーティング制限は、PSTN エンドポイントを含む会議にのみ適用されます。

- PSTN ゲートウェイを使用して電話会議を PSTN にブリッジするネットワーク サイトと、開催者と参加者が接続しているネットワーク サイトがあります。

会議Location-Basedルーティング アプリケーションでは、異なるネットワーク サイトから同じSkype for Businessユーザーと PSTN エンドポイントへの参加を防止します。 会議の開催者が会議ルーティングに対して有効Location-Based会議アプリケーションは、次の制限を適用します。

- Skype for Business 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントによって異なり、この制限は参加しているエンドポイントが離れ、新しいエンドポイントが会議に参加するに応じて調整されます。 開催者と参加者が同じネットワーク サイトから Skype for Business 会議に参加している場合、PSTN エンドポイント、同じネットワーク サイトの別の参加者、別のネットワーク サイトの別の参加者、または不明なネットワーク サイトの参加者が参加できます。

- 開催者と参加者が異なるネットワーク サイトまたは不明なネットワーク サイトから会議に参加している場合、PSTN 通話が Location-Based ルーティングに対して有効になっている SIP トランクからの PSTN 呼び出しが入力された場合、PSTN エンドポイントは会議に参加できません。

- 開催者と参加者全員が同じネットワーク サイトから会議に参加し、PSTN から同じ会議に参加する参加者が存在する場合、別のネットワーク サイトの Skype for Business エンドポイントは会議に参加できません。

これらの会議Location-Basedルーティングの制限を次の表に示します。

|任意の時点での会議のユーザー|会議に参加できるユーザー|ユーザーが会議に参加できない|
|:-----|:-----|:-----|
|Skype for Business VoIP クライアント ユーザーを 1 つのネットワーク サイトから削除する  <br/> |Skype for Businessサイトから VoIP クライアント ユーザーを削除する  <br/> Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> VoIP Skype for Businessユーザーのフェデレーション  <br/> PSTN エンドポイントからのユーザー参加  <br/> |なし  <br/> |
|Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> |Skype for Business VoIP クライアント ユーザーを任意のサイトから削除する  <br/> Skype for Businessサイトから VoIP クライアント ユーザーを削除する  <br/> VoIP Skype for Businessユーザーのフェデレーション  <br/> |PSTN エンドポイント経由でのユーザー参加  <br/> |
|Skype for Businessサイトからの VoIP クライアント ユーザーの管理  <br/> |Skype for Businessサイトから VoIP クライアント ユーザーを削除する  <br/> Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> VoIP Skype for Businessユーザーのフェデレーション  <br/> |PSTN エンドポイント経由でのユーザー参加  <br/> |
|Skype for Businessの VoIP クライアント ユーザーと PSTN エンドポイントから参加しているユーザーを選択する  <br/> |Skype for Businessサイトから VoIP クライアント ユーザーを削除する  <br/> |Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> Skype for Businessネットワーク サイトから VoIP クライアント ユーザーを削除する  <br/> VoIP Skype for Businessユーザーのフェデレーション  <br/> |

電話会議のルーティング アプリケーションのLocation-Basedの特性を次に示します。

- Location-Based ルーティング制限が設定された会議にユーザーが参加できない場合、会議への呼び出しは拒否され、Skype for Business クライアントは通話が完了していないか、終了したと報告します。

- Location-Based ルーティングの適用を使用して会議に参加する PSTN エンドポイントは、Location-Based ルーティングが有効になっていないトランクを介してエンドポイントが参加する場合、その状態に関係なく会議に参加Location-Basedされません。

- PSTN への発信呼び出しを行いません SIP トランクを使用して仲介サーバーに接続された PBX システムは、SIP トランクが定義されているのと同じネットワーク サイトにある Skype for Business ユーザーと同じ強制を行います。 たとえば、PBX ユーザーと Skype for Business ユーザーが同じネットワーク サイトにある場合、PSTN エンドポイントは電話会議に参加できます。それ以外の場合、PBX ユーザーが Skype for Business ユーザーとは異なるネットワーク サイトにある場合、PSTN エンドポイントは会議に参加できません。

> [!NOTE]
> 累積的Skype for Business 4 では、次の表の動作を確認する必要があります。

|User|その他のパーティ|Action|結果|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Businessは PSTN 通話中です。 Skype for Business、電話を電話会議 (CAA) 自動応答エスカレートします。  <br/> |呼び出しがブロックされ、適切なエラー メッセージが表示されます。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Businessまたはフェデレーション ユーザー  <br/> |クライアントまたはフェデレーション ユーザーは、Skype for Business Mobile Location-Basedユーザーに VoIP 呼び出しを行い、いずれかのパーティが CAA にエスカレートします。  <br/> |エスカレーション呼び出しはブロックされ、適切なエラー メッセージが表示されます。  <br/> |

## <a name="consultative-call-transfers"></a>コンサルティング通話の転送

Location-Based ルーティングを Skype for Business 会議に適用する以外に、Location-Based 会議用ルーティング アプリケーションは、PSTN エンドポイントに送信するコンサルティング通話転送に Location-Based ルーティング制限を適用します。 コンサルティング呼び出し転送は、2 つの関係者間で確立された呼び出しで、1 人の関係者が新しいユーザーに通話を転送します。 たとえば、PSTN エンドポイントはユーザー A を呼び出します (Skype for Business呼び出し先)。 ユーザー A は、PSTN ユーザーをユーザー B に転送する必要Skype for Businessします。 ユーザー A は PSTN ユーザーとの通話を保留にし、ユーザー B を呼び出します。ユーザー B は PSTN ユーザーと話をすることに同意します。 ユーザー A は、保留通話をユーザー B に転送します。

**コンサルティング呼び出し転送の呼び出しフロー**

![会議図の場所ベースのルーティング。](../../media/LocationBasedRoutingForConferencing.jpg)

Location-Based ルーティングを有効にしたユーザーが PSTN エンドポイントのコンサルティング通話転送を開始すると (前の図に示すように)、PSTN ユーザーと Skype for Business ユーザー A の間の 1 つの通話、および Skype for Business ユーザー A と Skype for Business の間のもう 1 つの通話が作成されます。 ユーザー B。次の動作は、電話会議Location-Basedによって適用されます。

- PSTN 通話をルーティングする SIP トランクが、Skype for Business ユーザー B (つまり、転送先) があるネットワーク サイトに PSTN 通話を再ルーティングする権限がある場合は、通話転送が許可されます。それ以外の場合は、コンサルティング通話の転送がブロックされます。 この承認は、PSTN エンドポイントにアクティブな呼び出しをルーティングする SIP トランクと同じネットワーク サイトにある転送先の場所に基づいて実行されます。

- 着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Skype for Business ユーザー B) があるネットワーク サイトへの通話のルーティングが承認されていない場合、または転送先が不明なネットワーク サイトにある場合、PSTN エンドポイントへのコンサルティング通話転送 (つまり、通話転送ターゲット) がブロックされます。

次の表では、Location-Based通話転送用の電話会議Location-Basedによってルーティング制限がどのように適用されるのかについて説明します。 PBX エンドポイントはネットワーク サイトに直接関連付けられるものではありませんが、PBX が接続されている SIP トランクにはネットワーク サイトを割り当てることができます。 したがって、PBX エンドポイントをネットワーク サイトに間接的に関連付けできます。


|通話転送先のネットワーク サイト|通話転送ターゲットのネットワーク サイト|動作|
|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |Skype for Businessのユーザー (サイト 1)  <br/> |コンサルト転送が許可されます  <br/> |
|PSTN エンドポイント  <br/> |Skype for Businessサイト (サイト 2) のユーザーを管理する  <br/> |コンサルト転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |Skype for Business不明なネットワーク サイトのユーザーを管理する  <br/> |コンサルト転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |フェデレーション Skype for Business ユーザー  <br/> |コンサルト転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |同じサイト内の PBX エンドポイント (サイト 1)  <br/> |コンサルト転送が許可されます  <br/> |
|PSTN エンドポイント  <br/> |別のサイトの PBX エンドポイント (サイト 2)  <br/> |コンサルト転送は許可されません  <br/> |
|同じサイト内の PBX エンドポイント (サイト 1)  <br/> |PSTN エンドポイント  <br/> |コンサルト転送が許可されます  <br/> |
|別のサイトの PBX エンドポイント (サイト 2)  <br/> |PSTN エンドポイント  <br/> |コンサルト転送は許可されません  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |Skype for Businessのユーザー (サイト 1)  <br/> |コンサルト転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |Skype for Businessサイト (サイト 2) のユーザーを管理する  <br/> |コンサルト転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |Skype for Business不明なネットワーク サイトのユーザーを管理する  <br/> |コンサルト転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |フェデレーション Skype for Business ユーザー  <br/> |コンサルト転送が許可されます  <br/> |

## <a name="requirements"></a>Requirements

会議Location-Basedルーティング アプリケーションでは、トポロジ内のすべての Front-End プールと Standard Edition サーバーに Skype for Business Server または Lync Server 2013 累積的な更新プログラム 2 を展開する必要があります。 これらのサーバー バージョンがトポロジ内の一部のサーバーにインストールされていない場合、Location-Based ルーティングの制限を会議やコンサルティング通話転送に完全に適用することはできません。

次の表は、サーバーの役割と、ルーティングをサポートするバージョンの組み合Location-Based示しています。


|Front-End プールのバージョン|仲介サーバーのバージョン|サポート|
|:-----|:-----|:-----|
|Skype for Business Server Lync Server 2013 累積的な更新プログラム 2  <br/> |Skype for Business Server Lync Server 2013 累積的な更新プログラム 2  <br/> |はい  <br/> |
|Lync Server 2013 累積的な更新プログラム 2  <br/> |Lync Server 2013 累積的な更新プログラム 1  <br/> |不要  <br/> |
|Lync Server 2013 累積的な更新プログラム 2  <br/> |Lync Server 2010  <br/> |不要  <br/> |
|Lync Server 2013 累積的な更新プログラム 2  <br/> |Office Communications Server 2007 R2  <br/> |不要  <br/> |
|Lync Server 2013 累積的な更新プログラム 1  <br/> |任意  <br/> |不要  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |不要  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |不要  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>会議用Location-Basedルーティングの構成

会議Location-Basedルーティング アプリケーションは、会議ルーティングの構成Location-Basedします。 主な構成は次のとおりです。

- 会議に参加する参加者の場所は、ネットワーク サイトに基づいて決定されます。 ネットワーク サイトとそれに関連付けられているネットワーク サブネットは、ルーティングを適用するために、Skype for Business Serverで定義Location-Based必要があります。

- 会議のルーティングLocation-Based適用するには、Skype for Businessのルーティングを有効にするLocation-Basedがあります。

- 会議に参加Location-Based PSTN エンドポイントのルーティングを強制するには、PSTN エンドポイントの接続に使用する SIP トランクを、会議ルーティング用Location-Based必要があります。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>会議のLocation-Basedを有効にする

会議Location-Basedルーティング アプリケーションは既定で無効になっています。 このアプリケーションを有効にする前に、アプリケーションに割り当てる適切な優先度を決定する必要があります。 この優先度を決定するには、管理シェルで次のコマンドレットSkype for Business Server実行します。

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

このコマンドレットでは、 \<Pool FQDN\> 会議アプリケーションのルーティングLocation-Based有効にするプールです。

このコマンドレットは、ユーザーがホストするアプリケーションの一Skype for Business Server、各アプリケーションの優先度の値を返します。 会議Location-Basedルーティング アプリケーションには、"UdcAgent" アプリケーションより大きく、"DefaultRouting"、"ExumRouting"、および "OutboundRouting" アプリケーションよりも小さい優先度の値を割り当てる必要があります。 会議用ルーティング アプリケーションLocation-Based割り当てるには、"UdcAgent" アプリケーションの優先度の値より 1 ポイント高い値を割り当てすることをお勧めします。

たとえば、"UdcAgent" アプリケーションの優先度値が "2" の場合、"DefaultRouting" アプリケーションの優先度値は "8"、"ExumRouting" アプリケーションの優先度値は "9"、"OutboundRouting" アプリケーションの優先度値は "10" である場合は、Location-Based 電話会議アプリケーションの優先度値 "3" を割り当てる必要があります。 これにより、他のアプリケーション (優先度: 0 ~ 1)、"UdcAgent" (優先度: 2)、Location-Based ルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting" (優先度: 9)、"ExumRouting" (優先度: 10) および "OutboundRouting" (優先度: 1) の順にアプリケーションの優先度が設定されます。

Location-Based 会議用ルーティング アプリケーションの適切な優先度の値を見つけたら、Front-End プールまたは Standard Edition Server ごとに次のコマンドレットを入力します。Location-Based ルーティングに対してユーザーが有効になっています。

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

次に例を示します。

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

このコマンドレットを使用した後、プール内のすべてのフロントエンド サーバー、または会議Standard Editionルーティング アプリケーションが有効になっている Location-Based サーバーを再起動します。

> [!IMPORTANT]
> Location-Based会議またはコンサルティング転送へのルーティングの適用は、該当するプール内のすべてのフロント エンド サーバーまたは Standard Edition サーバーが再起動されるまで適用されません。 前のコマンドレット **で -Critical** **$true** に設定すると、Skype for Business Serverサービスが直ちに再起動されます。 これらのサービスを直ちに再起動しない場合は、- **Critical** を **$false** に設定してから、 **Set-CsServerApplication** を使用して、サービスの再起動後に **-Critical** を **$true** に変更します。

Location-Based 会議用ルーティング アプリケーションが正常に有効にされ、すべての適用可能なサーバーが再起動されると、Location-Based ルーティングが有効になっている Skype for Business ユーザーが組織する会議はすべて、PSTN 有料バイパスを防止するために監視されます。


