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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Skype for Business で使用できるPolycom、HP、Mitel 製の電話の種類と、必要なライセンスについて説明します。 '
ms.openlocfilehash: 03f9a6d5cf3ac496c4828825e68f068ec98a14ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106443"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Skype for Business Online で使う電話を入手する

[] Skype for Business Online は、Skype for Business アプリよりも従来式の電話の機能性や操作性を利用したいユーザー向けに、デスクトップ電話に適合および対応しています。このトピックでは、Skype for Business Online での使用でサポートされる電話およびファームウェアのバージョンについて説明し、組織内で電話機をセットアップする際に役立つその他の情報を提供します。

> [!NOTE]
> Skype for Business は、Microsoft 365 および Office 365 の主要な通信方法として、Microsoft Teams に置き換えられる可能性があります。  詳細 [については、Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) でのインテリジェントなコミュニケーションの新しいビジョンを参照してください。
>
>サポートされているデバイスに関する最新の更新プログラムと最新の情報を取得するには、インテリジェントな通信を行う [Microsoft Teams デバイスを参照してください](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。
  
## <a name="supported-phones"></a>サポートされている電話
  
Microsoft は Polycom、Yealink、AudioCodes と密接に提携して、電話システムのパートナー IP 電話プログラム (PIP) を通じてさまざまなデバイスを開発および認定しています。
  
Skype for Business の新しい電話を注文する場合は、適切な製品 ID を持つ電話 *を購入することが重要です*。 このような製品 ID により、お客様は受け取った電話機が Skype for Business Online の対象バージョンがインストール済みのものであることを確認できます。
  
|||
|:-----|:-----|
|**電話機のパートナー** <br/> |**Skype for Business 固有の製品 ID** <br/> |
|Polycom  <br/> |製品 ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Polycom 電話機の詳細については、Poly ドキュメント ライブラリ [を参照してください](https://documents.polycom.com/category/voice)。
  
Yealink 電話機の詳細については [、「Skype for Business IP Phones」を参照してください](http://www.yealink.com/products_list_10.html#filter2)。
  
AudioCodes 電話機の詳細については、「[Skype for Business の IP 電話機](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)」をご覧ください。
  
> [!NOTE]
> Lync Phone Edition は Skype for Business Online でサポートされていますが、Microsoft Teams ではサポートされていません。 LPE プラットフォームのメインストリーム サポートは 2014 年 4 月 10 日に終了し、Lync Server 2013 の製品サポート ライフサイクルに合わせて 2023 年 4 月 11 日まで延長サポートが終了しました。 LPE のライフ サイクルの詳細については、 「[マイクロソフト製品ライフ サイクル](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO)」をご覧ください。 LPE CAP モデルは Skype for Business Online でサポートされません。
>
> 今年の後半、Office 365 では、1.2 より前のバージョンの TLS はサポートされていません。 LPE の基盤となるオペレーティング システムでは TLS 1.2 をサポートしていないため、LPE の Office 365 への接続はサポートされなくなります。 詳細については、「[Office 365での TLS 1.2 の必須使用に対する準備](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。
  
## <a name="supported-firmware"></a>サポートされているファームウェア

これは、サポートされている電話が電話システムで動作するために必要な最低限のソフトウェア リリースです。
  
||||
|:-----|:-----|:-----|
|**電話機の種類** <br/> |**最小限のファームウェア** <br/> |**リリース日** <br/> |
|最適化済み (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |2015 年 5 月  <br/> |
|認定済み Polycom VVX シリーズ  <br/> |5.4.0A  <br/> |2015 年 12 月  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |2017 年 2 月  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |2016 年 12 月  <br/> |

現在の認定済みファームウェア バージョンの詳細については [、Skype for Business IP Phone を参照してください](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

> [!NOTE]
> ユーザーを Skype for Business Online に移行する前に、オンプレミスの展開用にセットアップした Lync Phone Edition (LPE) の電話機を、最低限のまたはそれ以降の必要なファームウェアに更新する必要があります。携帯電話のファームウェアを更新する前にユーザーをオンプレミスから Skype for Business Online に移行した場合、それらの電話機は Skype for Business Online に接続できません。 
  
## <a name="required-licenses"></a>必要なライセンス

Skype for Business Online の電話機には、ユーザー ライセンス以外の追加の Microsoft ライセンスは必要ありません。必要なユーザー ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
  
製造元のライセンス モデルは、Open SIP と Skype for Business 認定済みファームウェアとの間で異なる可能性があります。認定済みのモデルを Open SIP ファームウェアで用途変更する場合は、製造元にファームウェアのライセンス要件について確認する必要があります。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Online に接続された電話機能セット

すべてのデバイスの機能および性能については、製造元のユーザー ガイドを確認してください。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**機能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|ユーザー資格情報でのサイン イン  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |なし  <br/> |
|PC (ペアリング) 経由のサイン イン、Windows のみ  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|(Web サイン イン) 使用でのサイン イン  <br/>  <br/> **注:** 展開ガイドのサポート可能性マトリックスを確認します。           |はい  <br/> |はい  <br/> |はい  <br/> |なし  <br/> |
|シングルクリックでの会議への参加  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|クリックしてダイヤル (ペアリング)  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|会議のコントロール  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|ビジュアル ボイスメール  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|電話のロック  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|デバイスの更新  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|インバンド プロビジョニング  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|QoE  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |なし  <br/> |
|ログのアップロード  <br/> <br/> **注:** 現在、すべてのログは Microsoft サポート チームにのみアップロードされます。通話記録への顧客のアクセスはまだ利用できません。           |はい  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|先進認証  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |なし  <br/> |
|複数の緊急電話番号  <br/> |あり  <br/> |いいえ  <br/> |いいえ  <br/> |あり  <br/> |
|Exchange の予定表の統合*  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |はい  <br/> <br/> **注:** PC のテザリングが必要           |
|プレゼンス統合  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|企業ディレクトリ  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |
|デリゲーション  <br/> |あり  <br/> |はい  <br/> |はい  <br/> |なし  <br/> |
|連絡先の写真の統合  <br/> |なし  <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |
||||||

     
> [!NOTE]
> CX 600 またはその他の Aries 社の電話機は、多要素認証 (MFA) をサポートしません。 MFA を強制的に実行すると、これらのデバイスではサインインに失敗します。 これらのデバイスでは、認証に組織の ID のみを使用する必要があります。
 
## <a name="what-else-should-you-know"></a>その他の情報
詳細な設定手順については、「[Skype for Business Online 電話機の展開レポート](deploying-skype-for-business-online-phones.md)」をご覧ください。

## <a name="related-topics"></a>関連項目
[Skype for Business および Microsoft Teams のサービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)

[電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
