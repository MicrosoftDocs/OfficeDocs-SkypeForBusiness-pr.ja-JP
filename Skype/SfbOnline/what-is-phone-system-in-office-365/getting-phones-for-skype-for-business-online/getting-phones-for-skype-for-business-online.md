---
title: Skype for Business Online で使う電話を入手する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn which phones work with Skype for Business from Polycom, HP, and Mitel, and the required licenses. '
ms.openlocfilehash: 7efddd118ca80f0610f287746e0f14ee0146d3c3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="getting-phones-for-skype-for-business-online"></a>Skype for Business Online で使う電話を入手する

[] Skype for Business Online は、Skype for Business アプリよりも従来式の電話の機能性や操作性を利用したいユーザー向けに、デスクトップ電話に適合および対応しています。このトピックでは、Skype for Business Online での使用でサポートされる電話およびファームウェアのバージョンについて説明し、組織内で電話機をセットアップする際に役立つその他の情報を提供します。
  
最新の更新プログラムとサポートされているデバイス上のほとんどの最新の情報を取得するのには、[デバイスのカタログをビジネス用の Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog)を参照してください。
  
## <a name="supported-phones"></a>サポートされる電話

ビジネス オンライン ユーザーの Skype は、*ビジネス電話の Skype の認定*のいくつかのモデルから選択することができ、Lync の電話のエディション (LPE) を実行している電話はビジネスのデバイスの[Skype でのオンライン ビジネスのカテゴリの Skype の下に表示カタログ](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
Office 365 での電話システムと Skype for Business Server のためのパートナー IP 電話プログラム (PIP) を通して広範なデバイスを開発および認定するために、Polycom、Yealink、AudioCodes と提携し、緊密に協業を進めています。
  
ビジネス用の Skype の新しい電話をオーダーするときは、*適切な製品 ID*の電話を購入する重要です。 このような製品 ID により、お客様は受け取った電話機が Skype for Business Online の対象バージョンがインストール済みのものであることを確認できます。
  
|||
|:-----|:-----|
|**電話機のパートナー** <br/> |**Skype for Business 固有の製品 ID** <br/> |
|Polycom  <br/> |製品 ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Polycom 電話機の詳細については、「[マイクロソフト対応音声ソリューション](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)」をご覧ください。
  
Yealink 電話の詳細については、[ビジネスの IP 電話の Skype](http://www.yealink.com/products_list_10.html#filter2)を参照してください。
  
AudioCodes 電話機の詳細については、「[Skype for Business の IP 電話機](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)」をご覧ください。
  
> [!NOTE]
> Lync Phone Edition は Skype for Business Online でサポートされます。LPE プラットフォームのメインストリーム サポートは 2014 年 4 月 10 日に終了します。延長サポートは Lync Server 2013 の製品サポート期間に合わせて 2023 年 4 月 11 日までになります。LPE のライフサイクルの詳細については、「[Microsoft 製品ライフサイクル](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO)」をご覧ください。LPE CAP モデルは Skype for Business Online でサポートされません。
  
## <a name="supported-firmware"></a>サポートされるファームウェア

サポート対象の電話で、Office 365 の電話システムと機能する必要な最低限のソフトウェア リリースは次のとおりです。
  
||||
|:-----|:-----|:-----|
|**電話機の種類** <br/> |**最小限のファームウェア** <br/> |**リリース日** <br/> |
|最適化済み (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |2015 年 5 月  <br/> |
|認定済み Polycom VVX シリーズ  <br/> |5.4.0A  <br/> |2015 年 12 月  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |2017 年 2 月  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |2016 年 12 月  <br/> |
   
> [!NOTE]
> ユーザーを Skype for Business Online に移行する前に、オンプレミスの展開用にセットアップした Lync Phone Edition (LPE) の電話機を、最低限のまたはそれ以降の必要なファームウェアに更新する必要があります。携帯電話のファームウェアを更新する前にユーザーをオンプレミスから Skype for Business Online に移行した場合、それらの電話機は Skype for Business Online に接続できません。 
  
## <a name="required-licenses"></a>必要なライセンス

Skype for Business Online の電話機には、ユーザー ライセンス以外の追加の Microsoft ライセンスは必要ありません。必要なユーザー ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
  
製造元のライセンス モデルは、Open SIP と Skype for Business 認定済みファームウェアとの間で異なる可能性があります。認定済みのモデルを Open SIP ファームウェアで用途変更する場合は、製造元にファームウェアのライセンス要件について確認する必要があります。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Online 接続済み電話機の機能セット

すべてのデバイスの機能および性能については、製造元のユーザー ガイドを確認してください。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**機能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|ユーザー資格情報でのサイン イン  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|PC (ペアリング) 経由のサイン イン、Windows のみ  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|(Web サイン イン) 使用でのサイン イン  <br/>  <br/> **注:** 展開ガイドの「サポート ・ マトリックスをを確認してください。           |あり  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|シングルクリックでの会議への参加  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|クリックしてダイヤル (ペアリング)  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|会議のコントロール  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|ビジュアル ボイスメール  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|電話のロック  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|デバイスの更新  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|インバンド プロビジョニング  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|QoE  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|ログのアップロード  <br/> <br/> **注:** マイクロソフト サポート チームのみにすべてのログをアップロードする現在、電話ログへのアクセスは利用できます。           |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|先進認証  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|複数の緊急電話番号  <br/> |あり  <br/> |なし  <br/> |なし  <br/> |あり  <br/> |
|Exchange の予定表の統合*  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> <br/> **注:** PC にケーブル接続する必要があります。           |
|プレゼンス統合  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|企業ディレクトリ  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|デリゲーション  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|連絡先の写真の統合  <br/> |なし  <br/> |あり  <br/> |なし  <br/> |あり  <br/> |
||||||

    > [!NOTE]
    > CX 600 or any other Aries phones don't support multifactor authentication (MFA). If you force MFA, these devices will fail to sign-in. These devices must use only Org ID for authetication.
   
## <a name="what-else-should-you-know"></a>その他の情報
詳細な設定手順については、「[Skype for Business Online 電話機の展開レポート](deploying-skype-for-business-online-phones.md)」をご覧ください。

## <a name="related-topics"></a>関連トピック
[Skype for Business および Microsoft Teams のサービス電話番号の取得](../getting-service-phone-numbers.md)

[Office 365 での電話システムで利用できる機能](../here-s-what-you-get-with-phone-system.md)

[国および地域ごとの電話会議および通話プランの利用可能性](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 