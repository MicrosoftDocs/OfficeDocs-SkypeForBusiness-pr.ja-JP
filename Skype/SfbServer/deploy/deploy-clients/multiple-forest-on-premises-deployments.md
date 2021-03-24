---
title: Skype Room System 複数のフォレストのオンプレミス展開
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
description: 複数のフォレストのオンプレミス環境に Skype Room System を展開する方法については、このトピックを参照してください。
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093531"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Room System 複数のフォレストのオンプレミス展開
 
複数のフォレストのオンプレミス環境に Skype Room System を展開する方法については、このトピックを参照してください。
  
> [!NOTE]
> 複数のフォレストに展開するには、Skype Room System で 2014 Exchange Server 2013 CU6 がリリースされている必要があります。 Skype Room System の既存のメールボックスを再使用しないようにします。 Skype Room System の新しい (古いメールボックスを削除し、再作成する) リソース メールボックスを使用します。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または復元 [する」を参照してください](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
メールボックスを作成した後、メールボックスを構成Set-CalendarProcessingを使用できます。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。 Skype Room System 用の Exchange リソース メールボックスを作成した後、「単一フォレストのオンプレミス展開での Skype for Business の Skype ルーム システム アカウントの有効化」の手順に従って、Skype for Business のアカウントを有効にします。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>オプション 1: 新しいリソース メールボックスを作成する

複数フォレスト環境に Skype Room System を展開するには、次の方法を実行します。
  
1. Active Directory (認証フォレスト) でリンクユーザー (LinkedRoomTest) を作成します。
    
2. 管理シェルで次のコマンドExchange Server実行します。
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>オプション 2: 既存のルーム メールボックスを Skype Room System (リンクされた) リソース メールボックスに変更する

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```