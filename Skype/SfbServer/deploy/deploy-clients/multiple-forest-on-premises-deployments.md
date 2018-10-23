---
title: 複数フォレストのオンプレミス環境での Skype Room System の展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 507040a1d8274817e7a4a0780135ee8f6642c77c
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699652"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>複数フォレストのオンプレミス環境での Skype Room System の展開
 
このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
  
> [!NOTE]
> 複数のフォレストに配置するには、Skype ルームのシステムには、Exchange Server 2013 CU6 が 2014 年 8 月 26 日にリリースが必要です。 Skype ルーム システムの既存のメールボックスを再使用しないでください。 使用して、新しい (古いメールボックスを削除して再作成) Skype ルーム システムのリソース メールボックスです。 メールボックスが削除されたことで失われた会議を復元する方法については、「[削除されたメールボックスの接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)」を参照してください。 
  
メールボックスを作成すると、Set-CalendarProcessing 使用してメールボックスを構成できるようになります。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 から 6 を参照してください。 Skype ルーム システム、Exchange リソース メールボックスを作成した後は、設置型展開の 1 つのフォレストでビジネス用の Skype の Skype ルーム システム アカウントの有効化の手順に従って、ビジネスの Skype のアカウントを有効にします。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>オプション 1: 新しいリソース メールボックスを作成する

複数のフォレスト環境では、Skype ルーム システムを展開します。
  
1. リンクされているユーザー (LinkedRoomTest) を Active Directory (Authentication Forest) に作成します。
    
2. Exchange Server の管理シェルで次のコマンドを実行します。
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>オプション 2: Skype ルーム システム (リンク) のリソース メールボックスを既存の会議室メールボックスを変更します。

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


