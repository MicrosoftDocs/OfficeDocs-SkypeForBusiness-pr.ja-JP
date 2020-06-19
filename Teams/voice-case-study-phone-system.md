---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786100"
---
# <a name="contoso-case-study-phone-system"></a>Contoso のケーススタディ: 電話システム

地理的な位置情報やその他の要因によっては、Contoso には以下のテレフォニーソリューションが使用されていました。

- サイトの種類 A: Skype for Business のエンタープライズボイス

- サイトの種類 B: 従来の従来のテレフォニーシステム

- サイトの種類 C: Skype for Business のエンタープライズボイスと従来の従来のテレフォニーシステムの組み合わせ


組織全体に対して Microsoft 電話システムソリューションを実装するために、Contoso は各サイトの種類を決定する必要がありました &mdash; &mdash; 。電話システムで公衆交換電話網 (PSTN) に接続するために使用されるオプションは、次のうちのどれですか。

- 通話プラン付きの電話システム 

- 直接ルーティングを通じて独自の PSTN キャリアを搭載した電話システム 

- 電話システムと通話プランと電話システムの組み合わせ (独自の PSTN キャリアと直接ルーティング経由)
 
組織に最適なソリューションを決定するために、Contoso は microsoft の[office](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)で使用されている Ignite 2019 セッション[通話](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)を使用しました。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>サイトの種類 A: Skype for Business のエンタープライズボイス 

Contoso Skype for Business のエンタープライズボイスはハブとスポークとして設定されました。 国内の Skype for Business のエンタープライズボイスユーザーに対して PSTN への接続が提供された地域で PSTN ゲートウェイを管理する場所がありました。 多くの場合、これらのサテライトオフィスには、独自のインターネット出口がありませんでした。 これらのユーザの番号は、既存の SBC に接続している SIP トランクに属しています。 

既に展開されている SBC が直接ルーティングとメディアのバイパスを認定しているかどうかを判断するために、Contoso は、[ダイレクトルーティング用に認定されたセッション境界コントローラーのリスト](direct-routing-border-controllers.md)を確認しました。  

ユーザーのダイヤルの傾向は、ユーザーが Skype for Business クライアントをピアツーピアオーディオで利用できる場合でも、内線番号を使用して、従来のテレフォニーシステムでユーザーをダイヤルすることでした。 

Contoso は以下の質問に基づいて決定しています。

- Q&a. オンプレミスの展開によって提供される機能を保持する必要がありますか?<br>
  、. X 

- Q&a. サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?<br>
  、. X 

- Q&a. 現在のサードパーティの携帯電話会社を保持する必要がありますか?<br> A. ○ (規制対象国) といいえ 

- Q&a. SBCs では ROI を導入する必要がありますか?<br> A. はいといいえ  

- Q&a. Microsoft PSTN 通話プランはこの地域で利用できますか?<br> A. はいといいえ 

お客様の質問に対する回答に基づいて、Contoso は以下のことを決定しました。

- 通話プランがある電話システムで PSTN 通話プランを利用できる地域に配置されているユーザーを移動します。 

- PSTN 通話プランが利用可能な地域内に存在しないユーザー、SBCs の ROI がまだ満たされているサイト内のユーザー、および直接ルーティングを使用して電話システムに電話をかけている国に居住しているユーザーを移動します。 

次の図は、最初の Skype for Business のエンタープライズ Voip の展開と、この展開が Microsoft の通話プランと直接ルーティングの両方に移行された方法を示しています。

![前と後の状態を示す図](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>サイトの種類 B: 従来の従来のテレフォニーシステム

Contoso には、従来のテレフォニーシステムを活用した多くのオフィスがありました。 他のユーザーには、電子1.64 電話番号が付いているユーザーのサブセットがありましたが、内線番号しかありませんでした。 これらの番号は、PSTN ゲートウェイに TDM トランクで存在しています。 サイト内ダイヤルは、内線番号の前にあるサイトコードを利用して、通話をルーティングする場所を決定して構成されました。 ユーザーのダイヤルの傾向は内線番号によって発信されました。   

Contoso は以下の質問に基づいて決定しています。

- Q&a. オンプレミスの展開によって提供される機能を保持する必要がありますか?<br>
  、. X 

- Q&a. サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?<br> A. はい

- Q&a. 現在のサードパーティの携帯電話会社を保持する必要がありますか?<br> A. いいえ 

- Q&a. Microsoft PSTN の通話プランは skype の地域で利用できますか?<br> A. はいといいえ 

お客様の質問に対する回答に基づいて、Contoso は以下のことを決定しました。 

- 通話プランがある電話システムで PSTN 通話プランを利用できる地域に配置されているユーザーを移動します。 

- PSTN 通話プランが電話システムで直接ルーティングされている地域に存在しないユーザーを移動します。 

- ビジネス上重要なアナログデバイスへの PSTN 接続を維持します。

次の図は、リモートサイトを使った元のレガシシステム展開と、ローカルメディア最適化によるダイレクトルーティング展開への移行を示しています。

**従来の従来の展開**  
 ![前と後の状態を示す図](media/voice-case-study-2.png)


**ダイレクトルーティングを使用した展開**

![前と後の状態を示す図](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>サイトの種類 C: Skype for Business のエンタープライズボイスと従来の従来のテレフォニーシステムの組み合わせ

Contoso Skype for Business のエンタープライズボイスユーザーの電話番号は、電話会社の SBC に対する SIP トランク上に存在します。 従来のテレフォニーシステムの番号は、PSTN ゲートウェイへの TDM トランクに搭載されています。   

Contoso は以下の質問に基づいて決定しています。

- Q&a. オンプレミスの展開によって提供される機能を保持する必要がありますか?<br>
  、. X 

- Q&a. サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?<br> A. いいえ 

- Q&a. 現在のサードパーティの携帯電話会社を保持する必要がありますか?<br> A. いいえ 

- Q&a. SBCs では ROI を導入する必要がありますか?<br> A. はいといいえ  

- Q&a. Microsoft の PSTN 通話プランはこの地域で利用できますか?<br> A. いいえ 

Contoso は、質問への回答に基づいて、次のことを決定しました。 

- 直接ルーティングが有効になる従来のテレフォニーユーザーの場合、Contoso は直接ルーティングの認定を受けているため、TDM トランクからの数を SBC の SIP トランクに移植しました。 

- 電話システムに移行するユーザーのサブセットをサポートし、従来のシステムによる継続的なルーティングを可能にするため、従来のテレフォニーシステムは、SBC への次のホップとして設定されています。   

- さらに、ユーザーの行動を変更して、サイト内およびサイト間拡張ダイヤルの依存関係を削除することもできます。これには、すべての内部通話に Teams を使用するためのガイダンスが用意されています。  

次の図は、元の Skype for Business のエンタープライズボイスと従来のテレフォニーシステムの展開と、ダイレクトルーティングを使用した混在展開への移行を示しています。

**元の混在展開** 
 ![以前の状態を示す図](media/voice-case-study-4.png)

**ダイレクトルーティング** 
 ![ による混在展開以前の状態を示す図](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話プラン

通話プランの構成要件を決定するために、Contoso は、[通話プランのコア展開の決定](calling-plan-landing-page.md#core-deployment-decisions)をレビューしています。 その結果、決定が行われました。 

- Q&a. ユーザーは国際電話を利用する必要がありますか?<br> A. はい 

- Q&a. 各ユーザーは、内側に電話番号を直接接続していますか?<br> 最新のものではありません。 すべてのユーザが有効になります。 

- Q&a. 発信者 ID のマスクや無効化を行いますか?<br> A. ユーザーの発信者番号は、Contoso の市内番号に対してマスクされます。 


## <a name="direct-routing"></a>ダイレクト ルーティング

Contoso は、電話システムと直接ルーティングで利用可能なものも含め、Office 365 の機能を常に最新の状態に保つことを Ignite しています。 技術リーダーと設計者は、Ignite 2019 で提供されているガイダンスを使用して、その方向を決定しました。  使用された主なセッション: 

- [Microsoft Teams のダイレクトルーティングを使用して成功を計画する](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接ルーティングの更新プログラム](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>構成

### <a name="calling-plans-sites"></a>通話プランのサイト

ライセンスを取得して電話番号をユーザーに割り当てるには、Contoso が[通話プランを設定](set-up-calling-plans.md)する手順に従います。 

電話番号を割り当てる必要があるユーザー数のため、Contoso は電話番号を割り当てるために PowerShell を使用することを決定しました。 他の設定に加えて、PowerShell を使用して数値を割り当てる方法については &mdash; &mdash; 、 [「Teams PowerShell の概要」](teams-powershell-overview.md)を参照してください。  

### <a name="direct-routing-sites"></a>ダイレクトルーティングサイト

Contoso のオンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続するために、Contoso の管理者は「[ダイレクトルーティングを構成](direct-routing-configure.md)する」の手順に従って、ガイダンスについては[microsoft Teams のビデオダイレクトルーティング](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)を確認しています。  Contoso は、認定された SBC ベンダーによるダイレクトルーティングの展開ドキュメントも参照しています。 

SBC と Microsoft Phone システムの間で直接ルーティングを構成した後は、Contoso が構成をテストする必要がありました。 これを行うために、Contoso 管理者は、 [Ignite 2019 でのダイレクトルーティングセッションの更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)で説明されている SIP テスタークライアントを使用しました。 SIP Tester クライアントスクリプトとドキュメントは、PowerShell スクリプトからダウンロードされ、ダイレクトルーティングセッションの境界コントローラー接続をテストしました。   


### <a name="local-media-optimization"></a>ローカルメディアの最適化

Contoso は、世界中のさまざまな地域でのローカルメディア最適化を活用しています。 Contoso でサポートされているシナリオは、[ダイレクトルーティング用のローカルメディア最適化](direct-routing-media-optimization.md)について説明しています。 ローカルメディア最適化の構成は、SBC ベンダーと Microsoft の両方のガイダンスに従って完了しました。 ローカルメディア最適化の構成手順は次のとおりです。 

- ユーザーと SBC サイトを構成する 

- Sbc ベンダー仕様に従って SBC を構成します。 

- ローカルメディア最適化に使用される各サイトに外部の信頼できる IP アドレスを追加する    

- ネットワークトポロジを定義する 

- 仮想ネットワークトポロジを定義する 

- モードを確認する: 常にローカルユーザーに対してのみバイパスまたは使用する 

## <a name="networking-considerations"></a>ネットワークに関する考慮事項

Contoso には、電話システムを有効にした後、長期間リモートで作業する必要がある多数のユーザーがいました。 特定の基幹業務アプリケーションへのアクセスに VPN を使用したユーザー。 VPN では、電話システムのユーザーが通話品質の低下を経験しています。 

この品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。これにより、内部アプリへの接続が VPN に残っている間も、Office 365 トラフィックがインターネットを通過できるようになりました。 VPN 分割トンネリングを実装するために、Contoso は、 [Office 365 用に vpn 分割トンネリングを実装するため](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)のガイダンスに従っています。  

 





