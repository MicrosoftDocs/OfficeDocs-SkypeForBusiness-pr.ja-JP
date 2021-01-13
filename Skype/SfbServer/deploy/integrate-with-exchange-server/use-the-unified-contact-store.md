---
title: 統合連絡先ストアを使用するために Skype for Business Server を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: '概要: 統合連絡先ストアを Exchange Server Skype for Business Server 用に構成します。'
ms.openlocfilehash: 4b96a0c4f3294146c987794ffce083c46d94bb48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833867"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>統合連絡先ストアを使用するために Skype for Business Server を構成する
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の統合連絡先ストアを構成します。
  
統合連絡先ストアを使用すると、ユーザーは 1 つの連絡先リストを保持し、それらの連絡先を Skype for Business、Microsoft Outlook 2013、および Microsoft Outlook Web App 2013 などの複数のアプリケーションで使用できます。 ユーザーの統合連絡先ストアを有効にした場合、そのユーザーの連絡先は Skype for Business Server に保存され、必要に応じて取得されません。 代わりに、連絡先は Exchange Server 2016 または Exchange Server 2013 に保存され、Exchange Web サービスを使用して取得されます。
  
> [!NOTE]
> 技術的には、連絡先情報は、ユーザーの Exchange メールボックスにある 2 つのフォルダーに格納されます。 連絡先自体は、エンド ユーザーに表示される Skype for Business 連絡先という名前のフォルダーに格納されます。連絡先に関するメタデータは、エンド ユーザーに表示されないサブフォルダーに格納されます。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

Skype for Business Server と Exchange Server の間のサーバー間認証が既に構成されている場合は、統合連絡先ストアも有効にしています。追加のサーバー構成は必要ありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、ユーザーの連絡先は、統合連絡先ストアではなく Skype for Business Server に保持されます。
  
統合連絡先ストアへのアクセスは、Skype for Business Server ユーザー サービス ポリシーを使用して管理されます。 ユーザー サーバー ポリシーには 1 つのプロパティ (UcsAllowed) のみがあります。このプロパティは、ユーザーの連絡先が格納されている場所を決定するために使用されます。 UcsAllowed が True ($True) に設定されているユーザー サービス ポリシーによってユーザーが管理されている場合、ユーザーの連絡先は統合連絡先ストアに格納されます。 UcsAllowed が False ($False) に設定されているユーザー サービス ポリシーによってユーザーが管理されている場合、ユーザーの連絡先は Skype for Business Server に保存されます。
  
Skype for Business Server をインストールすると、(グローバル スコープで構成された) 1 つのユーザー サービス ポリシーもインストールされます。 このポリシーの UcsAllowed 値は True に設定されています。つまり、既定では、ユーザーの連絡先は統合連絡先ストアに保存されます (これが展開および構成されている場合)。 すべてのユーザー連絡先を統合連絡先ストアに移行する場合は、何もする必要はありません。 
  
すべての連絡先を統合連絡先ストアに移行しない場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定して、すべてのユーザーの統合連絡先ストアを無効にできます。
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

グローバル ポリシーで統合連絡先ストアを無効にした後、統合連絡先ストアの使用を有効にするユーザーごとのポリシーを作成できます。これにより、一部のユーザーは連絡先を統合連絡先ストアに保持し、他のユーザーは引き続き連絡先を Skype for Business Server に保持できます。 次のようなコマンドを使用して、ユーザーごとのユーザー サービス ポリシーを作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

ポリシーが割り当てられると、Skype for Business Server はユーザーの連絡先を統合連絡先ストアに移行し始める。 移行が完了すると、ユーザーは自分の連絡先を Skype for Business Server ではなく Exchange に保存します。 移行が完了した時点でユーザーが Lync 2013 にログオンすると、メッセージ ボックスが表示され、プロセスを完了するために Skype for Business からログオフしてからログオンし戻すよう求めるメッセージが表示されます。 このユーザーごとのポリシーが割り当てられていないユーザーは、連絡先を統合連絡先ストアに移行されません。 これは、これらのユーザーがグローバル ポリシーによって管理され、統合連絡先ストアの使用がグローバル ポリシーで無効になっているためです。
  
ユーザーの連絡先が統合連絡先ストアに正常に移行されたことを確認するには、Skype for Business Server 管理シェルから [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) コマンドレットを実行します。
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

成功Test-CsUnifiedContactStore、ユーザー sip:kenmyer@ <span></span> litwareinc .com の連絡先が統合連絡先ストアに移行されたという意味 <span></span> です。
  
## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

統合連絡先ストアからユーザーの連絡先を削除する必要がある場合 (たとえば、ユーザーを Microsoft Lync Server 2010 に再ホームする必要がある場合、統合連絡先ストアを使用できなくなった場合など)、2 つの操作を行う必要があります。 最初に、統合連絡先ストアへの連絡先の格納を禁止する新しいユーザー サービス ポリシーをユーザーに割り当てる必要があります。 (つまり、UcsAllowed プロパティが有効に設定されている$False)。このようなポリシーが設定されていない場合は、次のようなコマンドを使用してポリシーを作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。
  
> [!NOTE]
> 場合によっては、ユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで、同じ効果を得られます。 たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。 その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除できます。 それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。 以前に割り当てられたユーザーごとのポリシーを割り当て解除するには、前に示したコマンドと同じコマンドを使用しますが、今回は PolicyName パラメーターを null 値に設定します。Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
統合連絡先ストアを操作する際には、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 ユーザーが Skype for Business Server にログオンすると、システムはユーザーのユーザー サービス ポリシーをチェックして、連絡先を統合連絡先ストアに保持する必要があるかどうかを確認します。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 回答がいいえの場合、Skype for Business Server はユーザーの連絡先を無視して次のタスクに進むだけになります。 つまり、UcsAllowed プロパティの値に関係なく、Skype for Business Server は統合連絡先ストアからユーザーの連絡先を自動的に移動しません。
  
つまり、ユーザーに新しいユーザー サービス ポリシーを割り当て後 [、Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) コマンドレットを実行して、ユーザーの連絡先を Exchange Server から Skype for Business Server に戻す必要があります。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

ユーザー サービス ポリシーを変更したが、コマンドレット Invoke-CsUcsRollback実行しない場合、Ken の連絡先は統合連絡先ストアから削除されません。 Ken Myer のユーザー Invoke-CsUcsRollback変更しない場合は、どうしますか。 その場合、Ken の連絡先は統合連絡先ストアから一時的に削除されます。 この削除は一時的なものですが、念頭に置いておく必要があります。 Ken の連絡先が統合連絡先ストアから削除された後、Skype for Business Server は 7 日間待機し、Ken に割り当てられているユーザー サービス ポリシーを確認します。 統合連絡先ストアのユーザーを有効にするポリシーが Ken に引き続き割り当てられている場合、Ken の連絡先は自動的に連絡先ストアに戻されます。 統合連絡先ストアから連絡先を完全に削除するには、統合連絡先ストアコマンドレットの実行に加えて、ユーザー サービス ポリシーInvoke-CsUcsRollbackがあります。
  
移行に影響を与える可能性がある変数の数が多く、アカウントが統合連絡先ストアに完全に移行される前にかかる時間を見積もるのは困難です。 ただし、一般に、移行はすぐに有効になるわけではありません。連絡先の数が少ない場合でも、移行が完了する前に 10 分以上かかる場合があります。
  

