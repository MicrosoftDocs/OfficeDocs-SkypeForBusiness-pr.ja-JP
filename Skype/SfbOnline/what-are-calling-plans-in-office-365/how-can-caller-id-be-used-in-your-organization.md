---
title: 呼び出し元 ID 利用する方法、組織内
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: CallingLineIdentity と呼ばれるポリシーを使用して、電話システムのユーザーの受信と送信の両方の呼び出しに呼び出し元の ID を制御できます。
ms.openlocfilehash: d658c292164556bb67845a08b519b9e78b6ff91d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>呼び出し元 ID 利用する方法、組織内

CallingLineIdentity と呼ばれるポリシーを使用して、電話システムのユーザーの受信と送信の両方の呼び出しに呼び出し元の ID を制御できます。
  
発信者番号機能は、PSTN への接続に関係なくすべての電話システムのユーザーが使用できます。
  
- オンラインの PSTN への接続
    
- ビジネス クラウド コネクタ ・ エディションの Skype での PSTN への接続を設置 (クラウド コネクタ版 1.4.2 が必要ですし、以降も)
    
- (内外のビジネス サーバー 2015 CU5 Skype が必要です) ビジネス サーバーの Skype での PSTN への接続を設置
    
> [!NOTE]
> このポリシーは、ビジネス 2015年サーバーの Skype では使用できません。 
  
## <a name="outbound-caller-id"></a>発信の呼び出し元の ID

PSTN 発信者番号通知の送信に使用できるオプションは次の 3 つです。
  
- 既定では、ユーザーに割り当てられている電話番号です。
    
- *サービス*として分類されている電話番号と Office 365 の電話の計画を呼び出すので*フリー ダイヤル*の番号は、在庫を番号します。 これは通常、組織の自動アテンダントまたは呼び出しのキューに割り当てられます。
    
- 匿名に設定します。
    
ただし、発信呼び出し元 ID のこれらの種類の電話番号を割り当てることはできません。
  
- 計画を呼び出す電話番号の*ユーザー*として分類されている任意の電話番号の番号の在庫
    
- Skype のビジネス サーバー設置型の電話番号
    
発信の呼び出し元の ID を設定するには、[ユーザーの発信者番号の設定](set-the-caller-id-for-a-user.md)を参照してください。
  
### <a name="end-user-control-of-outbound-caller-id"></a>発信呼び出し元 ID のユーザー コントロール

EnableUserOverride 属性は、**匿名**の発信者番号通知設定を変更するのには 1 つまたは複数のユーザーを有効にします。 LineURI または代替のいずれかの CallingIDSubstitute パラメーターを持つ CallingLineIdentity ポリシーが構成されている場合こののみ適用されます。 EnableUserOverride の既定値は、False です。
  
エンド ・ ユーザーは、Skype のビジネス デスクトップ クライアントの**呼び出しの転送の設定**] タブを使用して、**匿名**の呼び出し元の ID を設定できます。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**バージョン** <br/> |**サポート** <br/> |
|クイック実行  <br/> |2016 年 12 月 6 日 - 1611 (ビルド 7571.2072) のバージョンでリリースされた現在のチャネル  <br/> |あり  <br/> |
|クイック実行  <br/> |2017 年 2 月 22日 - 1701 (ビルド 7766.2060) のバージョンでリリースされた延期のチャネルの最初のリリース  <br/> |あり  <br/> |
|クイック実行  <br/> |チャネルは、2017 年 6 月 13日-1701 (ビルド 7766.2092) のバージョンのリリースを延期  <br/> |はい  <br/> |
|MSI  <br/> |Skype for Business  <br/> |なし  <br/> |
|Mac  <br/> |Skype for Business  <br/> |なし  <br/> |
   
## <a name="inbound-caller-id"></a>発信者番号通知を受信します。

BlockIncomingCallerID 属性では、PSTN 通話の着信の呼び出し元 ID をブロックします。 この属性を設定することができますが、ユーザー設定] ページで、エンド ・ ユーザーには使用できません。 オンラインの PSTN への接続のみで現在使用可能になります。
  
発信の呼び出し元の ID を設定するには、[ユーザーの発信者番号の設定](set-the-caller-id-for-a-user.md)を参照してください。
  
## <a name="related-topics"></a>[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)
電話番号の管理フォームのダウンロード

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 