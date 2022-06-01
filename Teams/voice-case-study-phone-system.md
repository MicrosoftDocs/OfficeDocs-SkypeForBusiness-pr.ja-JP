---
title: 'Contoso のケース スタディ: 多国籍企業の電話システム'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams多国籍企業向けの音声ケース スタディ: 電話システム'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823668"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso のケース スタディ: 多国籍企業の電話システム

Contoso は、地理的な場所やその他の要因に応じて、次のテレフォニー ソリューションを使用するオフィスを持っていました。

- サイトの種類 A: Skype for Business エンタープライズ VoIP

- サイト タイプ B: 従来のレガシ テレフォニー システム

- サイト タイプ C: Skype for Business エンタープライズ VoIPと従来のレガシ テレフォニー システムの組み合わせ


組織全体に対してMicrosoft 電話システム ソリューションを実装するには、Contoso はサイトの種類&mdash;ごとに、次のオプションのうち、公衆交換電話網 (PSTN) に接続するために電話システムで使用するオプションを決定&mdash;する必要がありました。

- 通話プランを使用した電話システム 

- ダイレクト ルーティングを使用した独自の PSTN キャリアを使用した電話システム 

- 通話プランとの電話システムの組み合わせと、ダイレクト ルーティングによる独自の PSTN キャリアとの電話システム
 
Contoso は、組織に適したソリューションを決定するために、[Teams音声ソリューション](/microsoftteams/cloud-voice-landing-page)とMicrosoft Teamsでの Ignite 2019 セッション通話の計画[を](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935)使用しました。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>サイトの種類 A: Skype for Business エンタープライズ VoIP 

Contoso Skype for Business エンタープライズ VoIPはハブとスポークとして設定されました。 国のSkype for Business エンタープライズ VoIP ユーザーに PSTN への接続を提供する PSTN ゲートウェイをリージョン内に維持する中央の場所がありました。 多くの場合、これらのサテライト オフィスには独自のインターネット エグレスがありませんでした。 これらのユーザーの番号は、既存の SBC に接続している SIP トランクに存在します。 

Direct Routing と Media Bypass に対して既にデプロイされている SBC が認定されているかどうかを確認するために、Contoso はダイレクト ルーティング [の認定を受けたセッション ボーダー コントローラーの一覧を](direct-routing-border-controllers.md)確認しました。  

ユーザーのダイヤルの習慣は、拡張機能を使用してレガシ テレフォニー システム上のユーザーにダイヤルすることでした。ユーザーがピアツーピア オーディオで使用できるSkype for Business クライアントを持っている場合でもです。 

Contoso は、次の質問に基づいて決定しました。

- Q。 オンプレミスのデプロイによって提供される機能を保持する必要がありますか?<br>
  A。 いいえ 

- Q。 サードパーティの PBX システムやその他のテレフォニー機器と相互運用する必要がありますか?<br>
  A。 いいえ 

- Q。 現在のサード パーティの通信事業者を保持する必要がありますか?<br> A。はい (規制対象の国) といいえ 

- Q。 SBC の ROI をデプロイする必要がありますか?<br> A。さあ何とも言えません  

- Q。 Microsoft PSTN 通話プランはこのリージョンで利用できますか?<br> A。さあ何とも言えません 

Contoso は、その質問に対する回答に基づいて、次のことを行うことにしました。

- PSTN 通話プランが利用できるリージョン内にあるユーザーを、通話プランを使用して電話システム移動します。 

- PSTN 通話プランが利用可能なリージョンにないユーザー、SBC の ROI がまだ満たされていないサイト内のユーザー、およびダイレクト ルーティングで電話システムするテレフォニー規制がある国に存在するユーザーを移動します。 

次の図は、最初のSkype for Business エンタープライズ VoIP展開と、この展開が Microsoft 通話プランとダイレクト ルーティングの両方に移行された方法を示しています。

![図は、前後の状態を示しています。](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>サイト タイプ B: 従来のレガシ テレフォニー システム

Contoso には、レガシ テレフォニー システムを活用する多くのオフィスがありました。 E1.64 電話番号を持つユーザーのサブセットが存在し、他のユーザーは内線番号しか持っていませんでした。 これらの番号は、PSTN ゲートウェイへの TDM トランクに存在します。 サイト内ダイヤルは、拡張機能の前にあるサイト コードを利用して、呼び出しをルーティングする場所を決定することによって構成されました。 ユーザーのダイヤルの習慣は、内線番号でダイヤルすることでした。   

Contoso は、次の質問に基づいて決定しました。

- Q。 オンプレミスのデプロイによって提供される機能を保持する必要がありますか?<br>
  A。 いいえ 

- Q。 サードパーティの PBX システムやその他のテレフォニー機器と相互運用する必要がありますか?<br> A。はい

- Q。 現在のサード パーティの通信事業者を保持する必要がありますか?<br> A。いいえ 

- Q。 Microsoft PSTN の通話プランはリージョンで利用できますか?<br> A。さあ何とも言えません 

Contoso は、その質問に対する回答に基づいて、次のことを行うことにしました。 

- PSTN 通話プランが利用できるリージョン内にあるユーザーを、通話プランを使用して電話システム移動します。 

- PSTN 通話プランが直接ルーティングを使用して電話システムできるリージョンにないユーザーを移動します。 

- ビジネス クリティカルなアナログ デバイスへの PSTN 接続を維持します。

次の図は、リモート サイトを使用した元のレガシ システムの展開と、ローカル メディアの最適化を使用したダイレクト ルーティング展開への移行を示しています。

**元のレガシ デプロイ** 
![図は、前後の状態を示しています。](media/voice-case-study-2.png)


**直接ルーティングを使用したデプロイ**

![前後の状態を示す図。](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>サイト タイプ C: Skype for Business エンタープライズ VoIPと従来のレガシ テレフォニー システムの組み合わせ

Contoso Skype for Business エンタープライズ VoIPユーザーの番号は、通信事業者から SBC への SIP トランクに存在します。 従来のテレフォニー システムの番号は、PSTN ゲートウェイへの TDM トランクに存在します。   

Contoso は、次の質問に基づいて決定しました。

- Q。 オンプレミスのデプロイによって提供される機能を保持する必要がありますか?<br>
  A。 いいえ 

- Q。 サードパーティの PBX システムやその他のテレフォニー機器と相互運用する必要がありますか?<br> A。いいえ 

- Q。 現在のサード パーティの通信事業者を保持する必要がありますか?<br> A。いいえ 

- Q。 SBC の ROI をデプロイする必要がありますか?<br> A。さあ何とも言えません  

- Q。 Microsoft の PSTN 通話プランはこのリージョンで利用できますか?<br> A。いいえ 

Contoso は、その質問に対する回答に基づいて、次のことを決定しました。 

- ダイレクト ルーティングを有効にするレガシ テレフォニー ユーザーの場合、Contoso は、SBC がダイレクト ルーティングの認定を受けたため、TDM トランクから SBC の SIP トランクに番号を移植しました。 

- 電話システムに移行するユーザーのサブセットをサポートし、レガシ システムを介した継続的なルーティングを許可するために、レガシ テレフォニー システムは SBC への次ホップとして設定されました。   

- さらに、ユーザーの動作の変更を促し、サイト間およびサイト内の拡張機能のダイヤルへの依存を取り除くために、Contoso はすべての内部呼び出しにTeamsを使用するためのガイダンスを提供しました。  

次の図は、元のSkype for Business エンタープライズ VoIPとレガシ テレフォニー システムの展開と、ダイレクト ルーティングを使用した混合デプロイへの移行を示しています。

**元の混合デプロイ**
![前の状態を示す図 1。](media/voice-case-study-4.png)

ダイレクト ルーティング
![**を使用した混合展開** 前の状態を示す図 2。](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話プラン

計画を呼び出すための構成要件を決定するために、Contoso は [通話プランのコアデプロイの決定を](calling-plan-landing-page.md#core-deployment-decisions)確認しました。 結果として得られた決定は次のとおりです。 

- Q。 ユーザーは国際電話を利用する必要がありますか?<br> A。はい 

- Q。 ユーザーはそれぞれ、直接内向きの DID 電話番号を持っていますか?<br> A. 今日ではありません。 有効になっているすべてのユーザーは、DID を受け取ります。 

- Q。 発信者 ID のマスクや無効化を行いますか?<br> A。ユーザーの呼び出し元 ID は、Contoso のローカル番号にマスクされます。 


## <a name="direct-routing"></a>ダイレクト ルーティング

Contoso は Ignite に出席し、電話 システムとダイレクト ルーティングで利用できる機能を含むOffice 365機能を最新の状態に保つ必要があります。 技術的なリーダーシップとアーキテクトは、Ignite 2019 で提供されたガイダンスを使用して、その方向を決定しました。  使用されたキー セッション: 

- [Microsoft Teamsダイレクト ルーティングを使用して成功を計画する](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [ダイレクト ルーティングの更新プログラム](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>構成

### <a name="calling-plans-sites"></a>プランサイトの呼び出し

ライセンスを取得し、ユーザーに電話番号を割り当てるには、「 [通話プランの設定](set-up-calling-plans.md)」の手順に従いました。 

電話番号を割り当てる必要があるユーザーの数が原因で、Contoso は PowerShell を使用して電話番号を割り当てることにしました。 Contoso が powerShell&mdash;の概要Teams使用した他の設定&mdash;に加えて、[PowerShell](teams-powershell-overview.md) を使用して番号を割り当てる方法について説明します。  

### <a name="direct-routing-sites"></a>ダイレクト ルーティング サイト

Contoso のオンプレミス テレフォニー インフラストラクチャをMicrosoft Teamsに接続するために、Contoso の管理者は[ダイレクト ルーティングの構成](direct-routing-configure.md)に関する手順に従い、[Microsoft Teamsのビデオ ダイレクト ルーティングに](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)関するガイダンスを確認しました。  Contoso は、認定された SBC ベンダーによるダイレクト ルーティング展開のドキュメントも参照しました。 

SBC と Microsoft 電話 システムの間でダイレクト ルーティングを構成したら、Contoso が構成をテストする必要がありました。 これを行うために、Contoso 管理者は、「[Ignite 2019 でのダイレクト ルーティング セッションの更新プログラム」で](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138)説明されている SIP テスター クライアントを使用しました。 SIP Tester クライアント スクリプトとドキュメントは、直接ルーティング セッション ボーダー コントローラー接続をテストするために PowerShell スクリプトからダウンロードされました。   


### <a name="local-media-optimization"></a>ローカル メディアの最適化

Contoso は、世界中のさまざまなリージョンでローカル メディアの最適化を活用する機会を得ました。 Contoso でサポートされているシナリオについては、「 [ダイレクト ルーティングのローカル メディアの最適化](direct-routing-media-optimization.md)」を参照してください。 ローカル メディアの最適化の構成は、SBC ベンダーと Microsoft の両方からのガイダンスに従って完了しました。 ローカル メディア最適化の構成手順は次のとおりです。 

- ユーザーサイトと SBC サイトを構成する 

- SBC ベンダーの仕様に従って SBC を構成します。 

- ローカル メディアの最適化に使用される各サイトに外部信頼済み IP アドレスを追加する    

- ネットワーク トポロジを定義する 

- 仮想ネットワーク トポロジを定義する 

- モードを決定する: ローカル ユーザーの場合は常にバイパスまたはのみ 

## <a name="networking-considerations"></a>ネットワークに関する考慮事項

Contoso には、電話システムを有効にした後、長時間リモートで作業する必要がある多数のユーザーがいました。 ユーザーは VPN を使用して特定の基幹業務アプリケーションにアクセスしました。 VPN では、電話システム ユーザーが通話品質の低下を経験しました。 

品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。これにより、内部アプリへの接続が VPN に残っている間、Office 365 トラフィックがインターネットを通過することができました。 CONTOSO は、VPN 分割トンネリングを実装するために、[Office 365用の VPN 分割トンネリングの実装に関するガイダンスに](/office365/enterprise/office-365-vpn-implement-split-tunnel)従いました。  

