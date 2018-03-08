---
title: "Office 365 への電話番号に転送します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PortingNumbersOverview
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: "Skype for Business、電話番号の移植する前にパスワードがわかってしに必要なものとに転送するポートの順序を作成する方法について説明します。"
ms.openlocfilehash: 1831880f200f42102233aa23a5e247b3efd973ca
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="transfer-phone-numbers-to-office-365"></a>Office 365 への電話番号に転送します。

Skype for Business、現在のサービス プロバイダーから自分の電話番号に転送する簡単です。Skype for Business を自分の電話番号をポートした後に Microsoft は、サービスのプロバイダーになり、料金を請求それらの電話番号をします。
  
電話番号に転送を開始する前に[転送する電話番号よく寄せられる質問](transferring-phone-numbers-common-questions.md)の情報を確認することをお勧めします。ダイヤルイン会議ブリッジ、自動応答またはその他のサービス番号サービス番号があれば、フリー ダイヤル電話番号も Skype for Business に転送するには、[管理の電話番号を表示する必要がある 999 より多くのユーザー (サブスクライバー) の電話番号組織](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)正しい形式をダウンロードして、お問い合わせに送信します。
  > [!NOTE]
  > 米国営業日にのみ、および祝日は休業または週末の電話番号に転送するためのポート注文の処理はします。 
  
## <a name="how-to-create-a-port-order-and-transfer-your-phone-numbers-to-skype-for-business"></a>ポートの順序を作成し、Skype for Business 電話番号に転送する方法
<a name="bk_LNPcountries_1"> </a>

  > [!NOTE]
  > ダイヤルイン会議ブリッジ、自動応答またはその他のサービス番号サービス番号があれば、フリー ダイヤル電話番号も Skype for Business に転送するには、[管理の電話番号を表示する必要がある 999 より多くのユーザー (サブスクライバー) の電話番号組織](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)) に正しい国/地域を選択し、正しい形式をダウンロードしてへのご協力に送信します。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. 左のナビゲーションでは、**音声**に移動 > **ポート受注]** > [**追加**] をクリックします。
    
4. [**新しいローカル番号ポートの順序**] ページで情報を読み、**では、始めましょう**] をクリックします。
    
5. **アカウント情報]**ページで、次を入力し、[**次へ**] をクリックします。
    
  - **アカウントの数**サービス プロバイダーまたは航空会社の番号を考慮します。
    
  - E.164 形式である必要があります**課金電話番号**(が必要ですを前に、番号を付加する記号 [+)。たとえば、北米番号を書式設定 + 1XXXYYYZZZZ を使用します。
    
  - **番号をブロック解除するのには、暗証番号 (pin)**暗証番号 (pin) で、現在のサービス プロバイダーまたは航空会社で必要な場合です。
    
  - **会社名**これは、会社または組織の名前です。
    
    > [!NOTE]
    > [**会社名**] ボックスは、スペースを含んだ 25 文字をのみ許可されます。会社の名前が 25 文字より長い場合は、名前の最初の 25 文字送信され、ポート順序は引き続き処理されます。
  
  - **Authorizing ユーザー**承認されたユーザーの名前です。
    
    > [!NOTE]
    > **Authorizing 人**] ボックスは、スペースを含んだ 15 文字をのみ許可されます。権限のある人の名前が 15 文字を超える場合は、名の最初の 15 文字送信され、ポート順序は引き続き処理されます。
  
  - **サービスのアドレス**サービス アカウントのアドレス。これで、サービス プロバイダーまたは carrier から請求書が表示されます。
    
  - **市区町村**、**状態**のサービス アドレスの**Zip**します。
    
6. [**数値**] ページで、E.164 形式の転送先としている電話番号を入力します。たとえば、北米番号を書式設定 + 1XXXYYYZZZZ を使用します。複数の電話番号をコンマを使用して区切ります。
    
    > [!NOTE]
    > 全ポートを実行する場合は、請求先の電話番号 (BTN) サービスをリストに含める必要があります。部分のポートを実行する場合は、このリストからサービスの請求先の電話番号 (BTN) にしておきます。 
  
    全ポートを実行する場合**は、現在の航空会社から自分のすべての電話番号を転送している**を選択します。部分のポートを実行する場合は、**転送は自分の電話番号の一部のみです**] を選びます。右の 1 つを選択した後は、**番号の移植性をチェック**] をクリックします。
    
7. [**続行**] をクリックします。
    
8. [**日付の転送**] ページで、**日**にドロップ ダウン日付を選択し [**開始時刻**] ドロップダウン、時刻を選択します (推定)、[**次へ**] をクリックします。
    
9. [**承認の文字**] ページで、次のボックスの各を確認します。[**署名**] ボックスで、[アカウントを変更する権限を持つユーザーを入力します。これは、[**アカウント情報**] ページで使用されている同じ名 > **Authorizing ユーザー**。[**次へ**] をクリックします。
    
10. **送信**ページの [**他のユーザー** **に通知を送信ポートの順序**] をクリックし、たいユーザーの他のメール アドレスを入力します。ポート順序は**ポート受注**] ページに表示されます。[**ステータス**] 列の順序の状態を表示することができます。**受注 ID**、**送信済み****日付の転送**および**状態**などのポート注文の詳細を表示することができます。詳細については、航空会社の名前を含む、操作ウィンドウでポートの注文を表示できます。
    
## <a name="what-happens-next"></a>次の動作ですか。
<a name="bk_LNPcountries_1"> </a>

ポート注文を送信し、受信する、が送信されますメール ポート注文を確認します。 
  
ポート、注文要求がチェックし、毎日更新し、の進捗状況とステータスを電子メールで通知されます。リクエストが拒否された場合、サポート チケットを開きのサポート チケット**ポート受注 ID**を提供することをお願いになります。Skype for Business 管理センター**音声**の ID を参照してポート順 > **ポート注文** > **受注 ID** ] 列。
  
## <a name="what-if-i-have-problems"></a>問題がある場合ですか。
<a name="bk_LNPcountries_1"> </a>

 **サービス アドレスでは、請求先住所と同じはありません。順序にアドレス情報は送信される理由は、引き続き元に戻して、お客様の請求書のコピーが一致してよいですか?**ほとんどの航空会社は、請求先のアドレスではなくサービス アドレス情報に基づいて移植情報を特定します。請求書のコピーを請求レコードなので、その可能性がありますサービス アドレスと同じ情報の提供移植されている電話番号。
  
 **べき注文時間がかかりすぎるを処理する場合ですか?**番号の移植非常に単純な/クイック プロセスを使用する必要があります。注文がよりも長くかかっている場合考える必要があること、ままの状態は、Skype for Business 管理センターで完了として表示する、サポート チケットを開いてください、ポート注文 ID を含める


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック
[電話番号のよく寄せられる質問を転送します。](transferring-phone-numbers-common-questions.md)

[さまざまなプランの呼び出し用の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急の呼び出し元の条項および条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急発信免責事項のラベル](https://go.microsoft.com/fwlink/?LinkID=692099)
