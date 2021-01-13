---
title: Location-Based Skype for Business Server での会議のルーティングの設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: コンサルティング通話転送を含む、Skype for Business Server エンタープライズ VoIP会議の場所に基づくルーティングの計画。
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825577"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based Skype for Business Server での会議のルーティングの設定

コンサルティング通話転送を含む、Skype for Business Server エンタープライズ VoIP会議の場所に基づくルーティングの計画。

Location-Basedルーティングを使用すると、通話内の関係者の場所に基づいて、VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを制限できます。 Location-Basedルーティングを使用すると、PSTN 有料Location-Basedバイパスを防ぐために、会議に対して Location-Based ルーティング ルールを適用できます。 アプリケーションはアクティブな会議を監視し、参加Location-Basedに基づいてルーティング制限を適用します。 またLocation-Based会議アプリケーションのルーティングを使用すると、PSTN エンドポイントが関係する取Location-Based転送にルーティングの制限を適用できます。

このLocation-Basedルーティング会議アプリケーションは、Skype for Business 会議に PSTN 有料バイパスを防止するためのメカニズムを提供します。 アプリケーションはアクティブな会議を監視し、Location-Based Skype for Business ユーザーの参加場所に基づいてルーティング制限を適用します。

次Location-Based条件が満たされた場合、Location-Based ルーティングを Skype for Business 会議に適用するかどうかを、ルーティング ルーティング アプリケーションが決定します。

- 会議の開催者は、会議のルーティングLocation-Basedできます。 Location-Based制限は、ルーティングが有効になっているユーザーが開催する会議にのみLocation-Basedされます。

- 少なくとも 1 人の会議参加者が PSTN エンドポイントである。 Location-Based制限は、PSTN エンドポイントを含む会議にのみ適用されます。

- PSTN ゲートウェイを使用して会議を PSTN にブリッジするネットワーク サイトと、開催者と参加者が接続するネットワーク サイトがあります。

会議Location-Basedルーティングを使用すると、異なるネットワーク サイトから同じ会議に Skype for Business ユーザーと PSTN エンドポイントを参加できません。 会議の開催者が Location-Based ルーティングに対して有効になっている場合、会議アプリケーションは次の制限を適用します。

- Skype for Business 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントによって異なり、この制限は参加したエンドポイントが会議から退出し、新しいエンドポイントが会議に参加するに応じて調整されます。 開催者と参加者が同じネットワーク サイトから Skype for Business 会議に参加している場合、PSTN エンドポイント、同じネットワーク サイトの別の参加者、別のネットワーク サイトの別の参加者、または不明なネットワーク サイトの参加者が参加できます。

- 開催者と参加者が異なるネットワーク サイトまたは不明なネットワーク サイトから会議に参加する場合、pstn 通話が Location-Based ルーティングが有効な SIP トランクから PSTN 通話が入る場合、PSTN エンドポイントは会議に参加できません。

- 開催者と参加者全員が同じネットワーク サイトから会議に参加し、PSTN から同じ会議に参加する参加者が存在する場合、別のネットワーク サイトの Skype for Business エンドポイントは会議に参加できません。

これらの会議Location-Basedルーティング制限の概要を次の表に示します。

|任意の時点での会議のユーザー|会議に参加できるユーザー|ユーザーは会議に参加できない|
|:-----|:-----|:-----|
|単一のネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> |同じネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> 別のネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> 不明なネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> フェデレーション Skype for Business VoIP クライアント ユーザー  <br/> PSTN エンドポイントからのユーザー参加  <br/> |なし  <br/> |
|不明なネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> |任意のサイトからの Skype for Business VoIP クライアント ユーザー  <br/> 不明なサイトからの Skype for Business VoIP クライアント ユーザー  <br/> フェデレーション Skype for Business VoIP クライアント ユーザー  <br/> |PSTN エンドポイント経由でのユーザーの参加  <br/> |
|異なるネットワーク サイトの Skype for Business VoIP クライアント ユーザー  <br/> |任意のネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> 不明なネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> フェデレーション Skype for Business VoIP クライアント ユーザー  <br/> |PSTN エンドポイント経由でのユーザーの参加  <br/> |
|単一のネットワーク サイトからの Skype for Business VoIP クライアント ユーザーと PSTN エンドポイントから参加するユーザー  <br/> |同じネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> |別のネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> 不明なネットワーク サイトからの Skype for Business VoIP クライアント ユーザー  <br/> フェデレーション Skype for Business VoIP クライアント ユーザー  <br/> |

電話会議アプリケーションのルーティングのLocation-Based特性を次に示します。

- Location-Based ルーティング制限がある場合、ユーザーが会議に参加できない場合、会議への呼び出しは拒否され、Skype for Business クライアントは通話が完了していないか、終了したと報告します。

- Location-Based Location-Based ルーティングが有効になっていないトランクを介してエンドポイントが参加する場合、Location-Based ルーティングの実施による会議に参加する PSTN エンドポイントは、その状態に関係なく会議に参加する制限されません。

- PSTN に通話を送信しない SIP トランク経由で仲介サーバーに接続された PBX システムには、SIP トランクが定義されているのと同じネットワーク サイトに存在する Skype for Business ユーザーと同じ適用が適用されます。 たとえば、PSTN エンドポイントが同じネットワーク サイトにある場合、PSTN エンドポイントは PBX ユーザーおよび Skype for Business ユーザーとの会議に参加できます。それ以外の場合、PBX ユーザーが Skype for Business ユーザーとは別のネットワーク サイトにある場合、PSTN エンドポイントは会議に参加できません。

> [!NOTE]
> Skype for Business 累積更新プログラム 4 では、次の表の動作を確認する必要があります。

|User|その他のユーザー|Action|結果|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は PSTN 通話中です。 次に、Skype for Business Mobile は通話を電話会議サービス (CAA) 自動応答エスカレートします。  <br/> |呼び出しがブロックされ、適切なエラー メッセージが表示されます。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> |クライアントまたはフェデレーション ユーザーは、Skype for Business Mobile Location-Based ルーティング ユーザーへの VoIP 呼び出しを行い、いずれかのユーザーが CAA にエスカレートします。  <br/> |エスカレーション呼び出しがブロックされ、適切なエラー メッセージが表示されます。  <br/> |

## <a name="consultative-call-transfers"></a>取次通話転送

Location-Based Routing to Skype for Business 会議の適用に加えて、Location-Based Routing for Conferencing アプリケーションは、PSTN エンドポイントに送信する取次通話転送に Location-Based ルーティング制限を適用します。 取次通話転送は、2 者間で確立された通話で、そのうちの 1 人が通話を新しいユーザーに転送します。 たとえば、PSTN エンドポイントはユーザー A (Skype for Business 呼び出し先) を呼び出します。 ユーザー A は、PSTN ユーザーをユーザー B (Skype for Business ユーザー) に転送する必要がある場合に決定します。 ユーザー A は PSTN ユーザーとの通話を保留にし、ユーザー B を呼び出します。ユーザー B は PSTN ユーザーと通話することに同意します。 ユーザー A は、通話を保留にした通話をユーザー B に転送します。

**取次通話転送の通話フロー**

![会議の場所に基づくルーティングの図](../../media/LocationBasedRoutingForConferencing.jpg)

Location-Based ルーティングが有効になっているユーザーが(前の図に示すように) PSTN エンドポイントの取次通話転送を開始すると、2 つのアクティブな通話が作成されます。1 つは PSTN ユーザーと Skype for Business ユーザー A の間、もう 1 つは Skype for Business ユーザー A と Skype for Business ユーザー B の間の通話です。次の動作は、Location-Based Routing for Conferencing アプリケーションによって適用されます。

- PSTN 通話をルーティングする SIP トランクが、Skype for Business ユーザー B (つまり、転送先) があるネットワーク サイトに PSTN 通話を再ルーティングする権限がある場合、通話転送が許可されます。それ以外の場合は、取次通話転送がブロックされます。 この承認は、PSTN エンドポイントにアクティブな通話をルーティングする SIP トランクと同じネットワーク サイト内にある転送先の場所に基づいて実行されます。

- 着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Skype for Business ユーザー B) が位置するネットワーク サイトに通話をルーティングする権限が与えられていない場合、または転送先が不明なネットワーク サイトにある場合、PSTN エンドポイントへの取次通話転送 (通話転送先) はブロックされます。

次の表では、取次Location-Based転送に対する電話会議用の Location-Based ルーティングによってルーティング制限がどのように適用されるのかについて説明します。 PBX エンドポイントはネットワーク サイトに直接関連付けられるものではありませんが、PBX が接続されている SIP トランクにネットワーク サイトを割り当てることができます。 したがって、PBX エンドポイントはネットワーク サイトに間接的に関連付けられる可能性があります。


|通話転送先のネットワーク サイト|通話転送ターゲットのネットワーク サイト|動作|
|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |同じネットワーク サイト (サイト 1) 内の Skype for Business ユーザー  <br/> |取次転送が許可されます  <br/> |
|PSTN エンドポイント  <br/> |異なるネットワーク サイト (サイト 2) 内の Skype for Business ユーザー  <br/> |取次転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |不明なネットワーク サイト内の Skype for Business ユーザー  <br/> |取次転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |フェデレーション Skype for Business ユーザー  <br/> |取次転送は許可されません  <br/> |
|PSTN エンドポイント  <br/> |同じサイト内の PBX エンドポイント (サイト 1)  <br/> |取次転送が許可されます  <br/> |
|PSTN エンドポイント  <br/> |別のサイト (サイト 2) 内の PBX エンドポイント  <br/> |取次転送は許可されません  <br/> |
|同じサイト内の PBX エンドポイント (サイト 1)  <br/> |PSTN エンドポイント  <br/> |取次転送が許可されます  <br/> |
|別のサイト (サイト 2) 内の PBX エンドポイント  <br/> |PSTN エンドポイント  <br/> |取次転送は許可されません  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |同じネットワーク サイト (サイト 1) 内の Skype for Business ユーザー  <br/> |取次転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |異なるネットワーク サイト (サイト 2) 内の Skype for Business ユーザー  <br/> |取次転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |不明なネットワーク サイト内の Skype for Business ユーザー  <br/> |取次転送が許可されます  <br/> |
|任意のサイトの PBX エンドポイント  <br/> |フェデレーション Skype for Business ユーザー  <br/> |取次転送が許可されます  <br/> |

## <a name="requirements"></a>要件

会議Location-Basedルーティングでは、Skype for Business Server または Lync Server 2013 の累積的な更新プログラム 2 がトポロジ内のすべての Front-End プールと Standard Edition サーバーに展開されている必要があります。 これらのサーバー バージョンがトポロジ内の一部のサーバーにインストールされていない場合、Location-Based ルーティング制限を会議および取次通話転送に完全に適用することはできません。

次の表に、サーバーの役割と、ルーティングをサポートするバージョンの組み合Location-Based示します。


|Front-End プールのバージョン|仲介サーバーのバージョン|サポート|
|:-----|:-----|:-----|
|Skype for Business Server または Lync Server 2013 の累積的な更新プログラム 2  <br/> |Skype for Business Server または Lync Server 2013 の累積的な更新プログラム 2  <br/> |必要  <br/> |
|Lync Server 2013 累積更新プログラム 2  <br/> |Lync Server 2013 累積更新プログラム 1  <br/> |いいえ  <br/> |
|Lync Server 2013 累積更新プログラム 2  <br/> |Lync Server 2010  <br/> |いいえ  <br/> |
|Lync Server 2013 累積更新プログラム 2  <br/> |Office Communications Server 2007 R2  <br/> |いいえ  <br/> |
|Lync Server 2013 累積更新プログラム 1  <br/> |任意  <br/> |いいえ  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |いいえ  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |いいえ  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>会議のLocation-Basedルーティングの構成

会議Location-Basedルーティングは、会議ルーティングの構成Location-Basedします。 主な構成は次のとおりです。

- 会議に参加する参加者の場所は、ネットワーク サイトに基づいて決定されます。 ネットワーク サイトとそれに関連付けられたネットワーク サブネットを Skype for Business Server で定義して、ネットワーク ルーティングLocation-Basedがあります。

- 会議のルーティングLocation-Based適用するには、Skype for Business の参加者が会議ルーティングに対してLocation-Basedがあります。

- 会議に参加Location-Based PSTN エンドポイントのルーティングを適用するには、PSTN エンドポイントの接続に使用する SIP トランクを、会議ルーティング用にLocation-Based必要があります。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>会議のLocation-Basedルーティングを有効にする

会議Location-Basedのルーティングは既定で無効になっています。 このアプリケーションを有効にする前に、アプリケーションに割り当てる適切な優先度を決定する必要があります。 この優先度を決定するには、Skype for Business Server 管理シェルで次のコマンドレットを実行します。

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

このコマンドレットでは \<Pool FQDN\> 、会議アプリケーションのLocation-Basedルーティングを有効にするプールです。

このコマンドレットは、Skype for Business Server によってホストされるアプリケーションの一覧と、各アプリケーションの優先順位の値を返します。 会議Location-Basedルーティングには、"UdcAgent" アプリケーションより大きく、"DefaultRouting"、"ExumRouting"、および "OutboundRouting" アプリケーションより小さい優先度値を割り当てる必要があります。 会議アプリケーションの Location-Based ルーティングには、"UdcAgent" アプリケーションの優先度値より 1 ポイント高い優先度値を割り当てすることをお勧めします。

たとえば、"UdcAgent" アプリケーションの優先度値が "2" の場合、"DefaultRouting" アプリケーションの優先度値は "8"、"ExumRouting" アプリケーションの優先度値は "9"、"OutboundRouting" アプリケーションの優先度値は "10" である場合は、Location-Based Routing for Conferencing アプリケーションに優先度値 "3" を割り当てる必要があります。 これにより、アプリケーションの優先度は、他のアプリケーション (優先度: 0 ~ 1)、"UdcAgent" (優先度: 2)、Location-Based ルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting" (優先度: 9)、"ExumRouting" (優先度: 10)、および "OutboundRouting" (優先度: 11) の順に配置されます。

Location-Based Routing for Conferencing アプリケーションの適切な優先度の値が見つけたら、ユーザーが Location-Based ルーティングを有効にしている各 Front-End プールまたは Standard Edition サーバーに対して次のコマンドレットを入力します。

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

例:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

このコマンドレットを使用した後、プール内のすべてのフロントエンド サーバーまたは会議アプリケーションの Location-Based ルーティングが有効になっている Standard Edition サーバーを再起動します。

> [!IMPORTANT]
> Location-Basedプール内のすべてのフロントエンド サーバーまたは Standard Edition サーバーが再起動されるまで、会議または取次転送へのルーティングの強制は適用されません。 上記の **コマンドレットで -Critical** **を $true** に設定すると、Skype for Business Server サービスが直ちに再起動されます。 これらのサービスをすぐに再起動しない場合は **、-Critical** を **$false** に設定してから **、Set-CsServerApplication** を使用して、サービスの再起動後に **-Critical** を **$true** に変更します。

会議アプリケーションの Location-Based ルーティングが正常に有効にされ、適用可能なすべてのサーバーが再起動されると、Location-Based ルーティングが有効になっている Skype for Business ユーザーが開催する会議はすべて監視され、PSTN 料金のバイパスが回避されます。


