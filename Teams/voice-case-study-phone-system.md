---
title: Teams Contoso のケース スタディ
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
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101033"
---
# <a name="contoso-case-study-phone-system"></a>Contoso のケース スタディ: 電話システム

地理的な場所や他の要因に応じて、Contoso は次のテレフォニー ソリューションを使用してオフィスを持っています。

- サイトの種類 A: Skype for Business エンタープライズ VoIP

- サイトの種類 B: 従来のレガシ テレフォニー システム

- サイトの種類 C: 従来のレガシ Skype for Business エンタープライズ VoIPシステムの組み合わせ


組織全体に Microsoft 電話 System ソリューションを実装するには、Contoso は、電話システム で使用されるサイトの種類ごとに、公衆交換電話網 &mdash; (PSTN) に接続するオプションを決定する &mdash; 必要がありました。

- 電話システムプランの使用 

- 電話システム直接ルーティングを使用して PSTN 通信業者と通信する 

- 通話プラン電話システム直接ルーティングを使用電話システム PSTN 通信事業者との組み合わせ
 
Contoso は、組織に適切なソリューションを決定するために[、Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)テレフォニー ソリューションと Ignite 2019 セッション[Calling in Microsoft Teams。](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>サイトの種類 A: Skype for Business エンタープライズ VoIP 

Contoso Skype for Business エンタープライズ VoIPハブとスポークとして設定されています。 PSTN ゲートウェイを維持する中央の場所は、PSTN への接続を国のユーザーに提供Skype for Business エンタープライズ VoIP場所でした。 多くの場合、これらの衛星オフィスには独自のインターネットエグレスがなかった。 これらのユーザーの番号は、既存の SBC に接続する SIP トランクに存在しました。 

既にデプロイされている SBC がダイレクト ルーティングとメディア バイパスの認定を受けたかどうかを確認するために、Contoso は直接ルーティングの認定を受けたセッション ボーダー コントローラーの一覧を [確認しました](direct-routing-border-controllers.md)。  

ユーザーのダイヤル習慣は、ユーザーがピアツーピア オーディオで使用可能な Skype for Business クライアントを持っている場合でも、拡張機能を使用してレガシ テレフォニー システムでユーザーをダイヤルする方法でした。 

Contoso は、次の質問に基づいて決定します。

- Q. オンプレミスデプロイによって提供される機能を保持する必要はありますか。<br>
  A. いいえ 

- Q. サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。<br>
  A. いいえ 

- Q. 現在のサードパーティの運送業者を保持する必要がありますか?<br> A.はい (規制対象の国)、いいえ 

- Q. SBC の ROI をデプロイする必要がありますか。<br> A.さあ何とも言えません  

- Q. Microsoft PSTN 通話プランは、このリージョンで利用できますか?<br> A.さあ何とも言えません 

Contoso は、質問に対する回答に基づいて、次の点を決定しました。

- PSTN 通話プランを利用できる地域にあるユーザーを、通話プランで電話システム移動します。 

- PSTN 通話プランを利用できる地域に存在しないユーザー、SBC の ROI がまだ満たされていないサイトに位置するユーザー、および直接ルーティングを使用して 電話システム に対するテレフォニー規制がある国に居住しているユーザーを移動します。 

次の図は、デプロイの初期Skype for Business エンタープライズ VoIPと、この展開が Microsoft 通話プランと直接ルーティングの両方に移行された方法を示しています。

![状態の前と後を示す図](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>サイトの種類 B: 従来のレガシ テレフォニー システム

Contoso には、レガシ テレフォニー システムを利用するオフィスが多数いました。 E1.64 電話番号を持つユーザーと、内線番号のみを持つユーザーのサブセットがあります。 これらの番号は、PSTN ゲートウェイへの TDM トランク上に存在します。 サイト内ダイヤルは、拡張機能の前にあるサイト コードを利用して、通話をルーティングする場所を決定することで構成されました。 ユーザーのダイヤルの習慣は、内線番号でダイヤルすることでした。   

Contoso は、次の質問に基づいて決定します。

- Q. オンプレミスデプロイによって提供される機能を保持する必要はありますか。<br>
  A. いいえ 

- Q. サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。<br> A.うん

- Q. 現在のサードパーティの運送業者を保持する必要がありますか?<br> A.違います 

- Q. Microsoft PSTN の通話プランは地域で利用できますか?<br> A.さあ何とも言えません 

Contoso は、質問に対する回答に基づいて、次の点を決定しました。 

- PSTN 通話プランを利用できる地域にあるユーザーを、通話プランで電話システム移動します。 

- PSTN 通話プランを直接ルーティングで使用できるリージョンに電話システム移動します。 

- 業務上重要なアナログ デバイスへの PSTN 接続を維持します。

次の図は、リモート サイトを使用した元のレガシ システムのデプロイと、ローカル メディアの最適化を使用したダイレクト ルーティング デプロイへの移行を示しています。

**元のレガシ デプロイ**  
 ![状態の前と後を示す図](media/voice-case-study-2.png)


**直接ルーティングを使用したデプロイ**

![状態の前と後を示す図](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>サイトの種類 C: 従来のレガシ Skype for Business エンタープライズ VoIPシステムの組み合わせ

Contoso Skype for Business エンタープライズ VoIPの番号は、SIP トランク上に存在し、運送業者から SBC に送信されます。 従来のテレフォニー システムの番号は、PSTN ゲートウェイへの TDM トランクに存在します。   

Contoso は、次の質問に基づいて決定します。

- Q. オンプレミスデプロイによって提供される機能を保持する必要はありますか。<br>
  A. いいえ 

- Q. サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。<br> A.違います 

- Q. 現在のサードパーティの運送業者を保持する必要がありますか?<br> A.違います 

- Q. SBC の ROI をデプロイする必要がありますか。<br> A.さあ何とも言えません  

- Q. Microsoft の PSTN 通話プランは、この地域で利用できますか?<br> A.違います 

Contoso は、質問に対する回答に基づいて、次の点を決定しました。 

- ダイレクト ルーティングが有効になるレガシ テレフォニー ユーザーの場合、Contoso は、SBC がダイレクト ルーティングの認定を受けたので、TDM トランクから SBC の SIP トランクに番号を移植しました。 

- 電話システム に移行するユーザーのサブセットをサポートし、レガシ システムを介したルーティングを継続するために、レガシ テレフォニー システムが SBC の次ホップとして設定されています。   

- さらに、ユーザーの行動の変更を促し、サイト間およびサイト内の内線番号のダイヤルに対する依存関係を削除するために、Contoso は、すべての内部呼び出しに Teams を使用するガイダンスを提供しました。  

次の図は、元のSkype for Business エンタープライズ VoIPレガシ テレフォニー システムのデプロイと、ダイレクト ルーティングを使用した混合デプロイへの移行を示しています。

**元の混合デプロイ** 
 ![状態の前を示す図](media/voice-case-study-4.png)

**ダイレクト ルーティングを使用した混合デプロイ** 
 ![状態の前を示す図](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話プラン

通話プランの構成要件を決定するために、Contoso は通話プランのコア デプロイの決定 [を確認しました](calling-plan-landing-page.md#core-deployment-decisions)。 その結果、次のような決定が行われた。 

- Q. ユーザーは国際電話を利用する必要がありますか?<br> A.うん 

- Q. ユーザーは、それぞれ直接内向き DID 電話番号を持っていますか?<br> A. 今日ではありません。 有効になっているすべてのユーザーは DID を受け取る。 

- Q. 発信者 ID のマスクや無効化を行いますか?<br> A.ユーザーの呼び出し元 ID は、Contoso のローカル番号にマスクされます。 


## <a name="direct-routing"></a>ダイレクト ルーティング

Contoso は Ignite に出席し、Office 365システムと直接ルーティングで利用できる機能電話最新の状態を取り入れる必要がありました。 技術的なリーダーシップとアーキテクトは、Ignite 2019 の間に提供されたガイダンスを使用して、方向を決定しました。  使用された主なセッション: 

- [直接ルーティングを使用して成功Microsoft Teams計画する](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [ダイレクト ルーティングの更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>構成

### <a name="calling-plans-sites"></a>通話プラン サイト

ライセンスを取得し、ユーザーに電話番号を割り当てるには、「通話プランを設定する [」の手順に従いました](set-up-calling-plans.md)。 

電話番号を割り当てる必要があるユーザーの数のために、Contoso は PowerShell を使用して電話番号を割り当てすることを決定しました。 他の設定に加えて PowerShell を使用して数値を割り当てる方法については &mdash; &mdash; [、「PowerShell の概要」Teams使用しました](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接ルーティング サイト

Contoso のオンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続するために、Contoso の管理者はダイレクト ルーティング[](direct-routing-configure.md)の構成に関するページの手順に従い、Microsoft Teams のビデオダイレクト[ルーティング](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)に関するガイダンスを確認しました。  Contoso は、認定された SBC ベンダーによる直接ルーティングの展開に関するドキュメントにも言及しました。 

SBC と Microsoft 電話 System の間で直接ルーティングが構成された後は、Contoso が構成をテストする必要があります。 これを行うには、Contoso の管理者は [、Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)のダイレクト ルーティングの更新セッションで説明した SIP Tester クライアントを使用しました。 SIP Tester クライアント スクリプトとドキュメントは、直接ルーティング セッション ボーダー コントローラー接続をテストするために PowerShell スクリプトからダウンロードされています。   


### <a name="local-media-optimization"></a>ローカル メディアの最適化

Contoso は、世界中の異なるリージョンでローカル メディアの最適化を利用する機会を見ていました。 Contoso でサポートされるシナリオについては、「直接ルーティングのための [ローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。 ローカル メディアの最適化の構成は、SBC ベンダーと Microsoft の両方からのガイダンスに従って完了しました。 ローカル メディアの最適化の構成手順は次のとおりです。 

- ユーザーサイトと SBC サイトを構成する 

- SBC ベンダーの仕様に従って SBC を構成します。 

- ローカル メディアの最適化に使用される各サイトに外部信頼済み IP アドレスを追加する    

- ネットワーク トポロジを定義する 

- 仮想ネットワーク トポロジを定義する 

- モードを決定する: ローカル ユーザーの場合は常にバイパスまたはのみ 

## <a name="networking-considerations"></a>ネットワークに関する考慮事項

Contoso には多数のユーザーがいましたが、ユーザーがリモートで作業を行う必要があったのは、そのユーザーがユーザーの作業を有効にした後、電話システム。 ユーザーは VPN を使用して特定の Line of Business アプリケーションにアクセスしました。 VPN を使用している間、電話システムユーザーは通話品質の低下を経験しました。 

品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。この方法では、内部アプリへの接続が VPN 上に残っている間、Office 365 トラフィックがインターネットを通過する許可を与えました。 VPN 分割トンネリングを実装するために、Contoso は「VPN 分割トンネリングを実装する」のガイダンス[に従](/office365/enterprise/office-365-vpn-implement-split-tunnel)Office 365。  

