---
title: "発信者の使い方、組織内で"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "発信者番号は、電話システムでユーザーの通話を着信および発信 CallingLineIdentity と呼ばれるポリシーを使用して制御できます。"
ms.openlocfilehash: f87718858507405e54643575825b264c6c1cbea1
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>発信者の使い方、組織内で

発信者番号は、電話システムでユーザーの通話を着信および発信 CallingLineIdentity と呼ばれるポリシーを使用して制御できます。
  
発信者の機能は PSTN への接続に関係なく、すべての電話システムでユーザーに利用できます。
  
- オンライン PSTN への接続
    
- Skype for Business クラウド コネクタのエディションとオンプレミス PSTN への接続 (クラウド コネクタ Edition 1.4.2 を必要と以降)
    
- Skype for Business Server が (Business Server 2015 CU5 とだけでなく、Skype が必要) とオンプレミス PSTN への接続
    
> [!NOTE]
> このポリシーは Skype for Business 2015 サーバーで利用できません。 
  
## <a name="outbound-caller-id"></a>外部の発信者番号

送信 PSTN 発信者の利用可能なは 3 つのオプションがあります。
  
- 既定では、ユーザーに割り当てられている電話番号。
    
- *サービス*として分類されている電話番号との電話の Office 365 のプランの呼び出し、*フリー ダイヤル*番号を在庫に番号します。通常は組織の自動応答または着信キューに割り当てられます。
    
- 匿名に設定します。
    
ただし、発信発信者のこれらの種類の電話番号を割り当てることはできません。
  
- 任意の電話番号で電話番号を呼び出すプラン*ユーザー*として分類されている番号の在庫
    
- Skype for Business Server 内部設置型の電話番号
    
外部の発信者番号を設定するには、[ユーザーの発信者番号を設定する](set-the-caller-id-for-a-user.md)を参照してください。
  
### <a name="end-user-control-of-outbound-caller-id"></a>外部の発信者番号のエンド ユーザー コントロール

EnableUserOverride 属性により、**匿名**の発信者番号の設定を変更するのには、1 つまたは複数のユーザー。これは、CallingLineIdentity ポリシー LineURI または代替のいずれかの CallingIDSubstitute パラメーターが設定されている場合にのみ利用できます。EnableUserOverride の既定値は、False です。
  
エンドユーザーは、**着信の転送の設定**] タブの [で Skype for Business デスクトップ クライアントを使用して、**匿名**の発信者番号を設定できます。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**バージョン** <br/> |**サポートされています。** <br/> |
|クイック実行  <br/> |現在のチャネル リリース 2016 年 12 月 6 日の [バージョン 1611 (ビルド 7571.2072)  <br/> |○  <br/> |
|クイック実行  <br/> |最初のリリースでは、延期チャンネルのリリース 2017 年 2 月 22日] - [バージョン 1701 (ビルド 7766.2060)  <br/> |○  <br/> |
|クイック実行  <br/> |チャンネルを 2017 年 6 月 13日 - バージョン 1701 (ビルド 7766.2092) にリリースの保留  <br/> |○  <br/> |
|MSI  <br/> |Skype for Business  <br/> |×  <br/> |
|Mac  <br/> |Skype for Business  <br/> |×  <br/> |
   
## <a name="inbound-caller-id"></a>着信の発信者番号

BlockIncomingCallerID 属性は、PSTN 通話を受信した発信者番号をブロックすることができます。この属性を設定することができますが、ユーザー設定のページで、エンドユーザーには使用できません。現在、オンライン PSTN への接続でのみ利用できます。
  
外部の発信者番号を設定するには、[ユーザーの発信者番号を設定する](set-the-caller-id-for-a-user.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック
[電話番号のよく寄せられる質問を転送します。](transferring-phone-numbers-common-questions.md)

[さまざまなプランの呼び出し用の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理します。](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急の呼び出し元の条項および条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急発信免責事項のラベル](https://go.microsoft.com/fwlink/?LinkID=692099)