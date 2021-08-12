---
title: SkypeRoom System 複数フォレストのオンプレミス展開
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数のフォレストのオンプレミスSkype Room System を展開する方法について説明します。
ms.openlocfilehash: dc1d7fa3a3ca7cbcf62f7c038fb8fd6b4fcedc84319452ec8eaf02781f311bf3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310066"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>SkypeRoom System 複数フォレストのオンプレミス展開
 
このトピックでは、複数のフォレストのオンプレミスSkype Room System を展開する方法について説明します。
  
> [!NOTE]
> 複数のフォレストに展開するには、Skype 2014 Exchange Server 2013 CU6 が 2014 年 8 月 26 日にリリースされている必要があります。 ルーム システムで既存のメールボックスを再使用Skype避ける。 新しい (古いメールボックスを削除して再作成する) リソース メールボックスを、Skypeに使用します。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスConnect[復元する」を参照してください](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
メールボックスを作成した後、メールボックスを構成Set-CalendarProcessingを使用できます。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。 Skype Room System 用の Exchange リソース メールボックスを作成した後、「単一フォレストのオンプレミス展開」の「Skype Room System Accounts for Skype for Business を有効にする」の手順に従って、Skype for Business のアカウントを有効にします。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>オプション 1: 新しいリソース メールボックスを作成する

複数フォレストSkypeにルーム システムを展開するには、次の方法を実行します。
  
1. Active Directory (認証フォレスト) でリンクユーザー (LinkedRoomTest) を作成します。
    
2. 管理シェルで次のコマンドExchange Server実行します。
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>オプション 2: 既存のルーム メールボックスをルーム システム (Skype) リソース メールボックスに変更する

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```