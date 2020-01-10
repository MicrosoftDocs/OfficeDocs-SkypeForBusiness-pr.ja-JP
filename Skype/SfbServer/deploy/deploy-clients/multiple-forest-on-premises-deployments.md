---
title: 複数フォレストのオンプレミス環境での Skype Room System の展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 13ff6b1dbf1c6ba0cf9c8effddaaae8f097de9ea
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003507"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>複数フォレストのオンプレミス環境での Skype Room System の展開
 
このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
  
> [!NOTE]
> 複数のフォレストに展開するために、Skype Room System は2014年8月26日にリリースされた Exchange Server 2013 CU6 を必要とします。 Skype Room システムの既存のメールボックスを再利用しないでください。 Skype Room System の新規 (古いメールボックスの削除と再作成) リソースメールボックスを使用します。 メールボックスの削除によって失われた会議を復元するには、「[削除されたメールボックスを接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)する」をご覧ください。 
  
メールボックスを作成すると、Set-CalendarProcessing 使用してメールボックスを構成できるようになります。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 から 6 を参照してください。 Skype Room System の Exchange リソースメールボックスを作成した後、「単一フォレストのオンプレミス展開」の「skype for Business の skype Room System アカウントを有効にする」の手順に従って、Skype for Business のアカウントを有効にします。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>オプション 1: 新しいリソース メールボックスを作成する

複数のフォレスト環境で Skype Room システムを展開するには、次の操作を行います。
  
1. リンクされているユーザー (LinkedRoomTest) を Active Directory (Authentication Forest) に作成します。
    
2. Exchange Server の管理シェルで次のコマンドを実行します。
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>オプション 2: 既存の会議のメールボックスを Skype Room System (リンク) リソースメールボックスに変更する

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


