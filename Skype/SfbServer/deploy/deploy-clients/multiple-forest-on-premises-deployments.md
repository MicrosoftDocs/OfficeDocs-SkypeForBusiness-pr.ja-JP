---
title: Skype Room System の複数フォレストのオンプレミス展開
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
description: このトピックでは、複数フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805747"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Room System の複数フォレストのオンプレミス展開
 
このトピックでは、複数フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。
  
> [!NOTE]
> 複数のフォレストに展開するには、2014 年 8 月 26 日にリリースExchange Server 2013 CU6 が Skype Room System に必要です。 Skype Room System の既存のメールボックスを再使用しないようにします。 Skype Room System 用の新しい (古いメールボックスを削除して、作成し再作成する) リソース メールボックスを使用します。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または [復元する」を参照してください](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
メールボックスを作成した後、メールボックスのSet-CalendarProcessingを構成できます。 詳細については、単一フォレストのオンプレミス展開の手順 3 . ~ 6. を参照してください。 Skype Room System 用の Exchange リソース メールボックスを作成した後、単一フォレストのオンプレミス展開で Skype for Business の Skype Room System アカウントを有効にする手順に従って、Skype for Business のアカウントを有効にします。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>オプション 1: 新しいリソース メールボックスを作成する

複数フォレスト環境に Skype Room System を展開するには:
  
1. Active Directory (認証フォレスト) にリンク ユーザー (LinkedRoomTest) を作成します。
    
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


