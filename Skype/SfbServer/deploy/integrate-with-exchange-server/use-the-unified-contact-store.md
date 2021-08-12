---
title: 統合Skype for Business Serverストアを使用するユーザーの構成
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
description: '概要: 連絡先と連絡先の統合連絡先ストアExchange Server構成Skype for Business Server。'
ms.openlocfilehash: 78953049394391517d229205e711e670701d9f857458673646e4022a178d3843
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295714"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>統合Skype for Business Serverストアを使用するユーザーの構成
 
**概要:** 2016 年または 2016 年Exchange Server 2013 年および 2013 年Exchange Server統合連絡先ストアを構成Skype for Business Server。
  
統合連絡先ストアを使用して、ユーザーは 1 つの連絡先リストを維持し、Skype for Business、Microsoft Outlook 2013、および Microsoft Outlook Web App 2013 を含む複数のアプリケーションでそれらの連絡先を使用できます。 ユーザーに対して統合連絡先ストアを有効にした場合、そのユーザーの連絡先はユーザーの連絡先にSkype for Business Serverに保存され、必要に応じて取得されます。 代わりに、連絡先は Exchange Server 2016 または Exchange Server 2013 に保存され、Exchange Web サービスを使用して取得されます。
  
> [!NOTE]
> 技術的には、連絡先情報は、ユーザーのメールボックスに含Exchangeされます。 連絡先自体は、エンド ユーザーに表示される Skype for Businessという名前のフォルダーに格納されます。連絡先に関するメタデータは、エンド ユーザーには表示されないサブフォルダーに格納されます。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

サーバー間のサーバー間認証Skype for Business Server Exchange Server構成されている場合は、統合連絡先ストアも有効にしています。追加のサーバー構成は必要ありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、ユーザー連絡先は統合連絡先ストアではなくSkype for Business Serverに保持されます。
  
統合連絡先ストアへのアクセスは、ユーザー サービス ポリシーを使用Skype for Business Server管理されます。 ユーザー サーバー ポリシーのプロパティは 1 つのみです (UcsAllowed)。このプロパティは、ユーザーの連絡先が格納されている場所を特定するために使用されます。 UcsAllowed が True ($True) に設定されているユーザー サービス ポリシーによってユーザーが管理されている場合、ユーザーの連絡先は統合連絡先ストアに保存されます。 UcsAllowed が False ($False) に設定されているユーザー サービス ポリシーによってユーザーが管理されている場合、連絡先は Skype for Business Server に保存されます。
  
サーバーをインストールSkype for Business Server、単一のユーザー サービス ポリシー (グローバル スコープで構成) もインストールされます。 このポリシーの UcsAllowed 値は True に設定されています。つまり、既定では、ユーザー連絡先は統合連絡先ストアに格納されます (これが展開および構成済みである場合)。 すべてのユーザー連絡先を統合連絡先ストアに移行する場合は、何もする必要はありません。 
  
すべての連絡先を統合連絡先ストアに移行しない場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定して、すべてのユーザーの統合連絡先ストアを無効にできます。
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

グローバル ポリシーで統合連絡先ストアを無効にした後、統合連絡先ストアを使用できるユーザーごとのポリシーを作成できます。これにより、一部のユーザーが連絡先を統合連絡先ストアに保持し、他のユーザーは連絡先を引き続き管理Skype for Business Server。 次のようなコマンドを使用して、ユーザーごとのユーザー サービス ポリシーを作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

ポリシーが割り当てられたら、Skype for Business Server連絡先を統合連絡先ストアに移行します。 移行が完了すると、ユーザーは自分の連絡先をユーザーではなく、Exchangeに保存Skype for Business Server。 移行が完了した時点でユーザーが Lync 2013 にログオンした場合は、メッセージ ボックスが表示され、Skype for Business からログオフし、プロセスを完了するためにログオンし戻すよう求めるメッセージ が表示されます。 このユーザーごとのポリシーが割り当てられていないユーザーは、連絡先を統合連絡先ストアに移行されません。 これは、これらのユーザーがグローバル ポリシーによって管理され、統合連絡先ストアの使用がグローバル ポリシーで無効になっているためです。
  
ユーザーの連絡先が統合連絡先ストアに正常に移行されたことを確認するには[、test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps)コマンドレットを Skype for Business Server 管理シェル内から実行します。
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

このTest-CsUnifiedContactStore成功すると、ユーザー sip:kenmyer@ <span></span> litwareinc .com の連絡先が統合連絡先ストアに移行 <span></span> されました。
  
## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

統合連絡先ストアからユーザーの連絡先を削除する必要がある場合 (たとえば、Microsoft Lync Server 2010 でユーザーを再ホームする必要がある場合、統合連絡先ストアを使用できなくなった場合など) は、2 つの操作を行う必要があります。 最初に、ユーザーに新しいユーザー サービス ポリシー (統合連絡先ストアに連絡先を保存することを禁止するポリシー) を割り当てる必要があります。 (つまり、UcsAllowed プロパティが設定されているポリシー$False)。このようなポリシーが設定されていない場合は、次のようなコマンドを使用してポリシーを作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。
  
> [!NOTE]
> 場合によっては、ユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで、同じ正味効果を実現できます。 たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。 その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除できます。 それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。 以前に割り当てられたユーザーごとのポリシーを割り当て解除するには、前に示したコマンドと同じコマンドを使用しますが、今回は PolicyName パラメーターを null 値に設定します。Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
統合連絡先ストアを操作する際には、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 ユーザーが Skype for Business Server にログオンすると、システムはユーザーのユーザー サービス ポリシーをチェックして、連絡先を統合連絡先ストアに保持するかどうかを確認します。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 答えがいいえの場合は、Skype for Business Serverの連絡先を無視して次のタスクに進む必要があります。 つまり、Skype for Business Server UcsAllowed プロパティの値に関係なく、ユーザーの連絡先が統合連絡先ストアから自動的に移動されません。
  
つまり、ユーザーに新しいユーザー サービス ポリシーを割り当て後[、Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps)コマンドレットを実行して、ユーザーの連絡先を Exchange Server から Skype for Business Server に戻す必要があります。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

ユーザー サービス ポリシーを変更するが、コマンドレットを実行しないInvoke-CsUcsRollback Ken の連絡先は統合連絡先ストアから削除されません。 Ken Myer のユーザー Invoke-CsUcsRollbackポリシーを変更しない場合は、どうしますか? その場合、Ken の連絡先は統合連絡先ストアから一時的に削除されます。 この削除は一時的なものであるという事実を念頭に置いておく必要があります。 Ken の連絡先が統合連絡先ストアから削除されると、Skype for Business Server は 7 日間待機し、Ken に割り当てられているユーザー サービス ポリシーを確認します。 Ken に引き続き統合連絡先ストアのユーザーを有効にするポリシーが割り当てられている場合、連絡先は自動的に連絡先ストアに戻されます。 統合連絡先ストアから連絡先を完全に削除するには、ユーザー サービス コマンドレットの実行に加えて、ユーザー サービス ポリシーをInvoke-CsUcsRollbackがあります。
  
移行に影響を与える可能性がある変数の数が多く、アカウントが統合連絡先ストアに完全に移行されるまでにかかる時間を見積もるのは困難です。 ただし、一般的なルールとして、移行はすぐには有効ではありません。少ない数の連絡先を移行する場合でも、移動が完了する前に 10 分以上かかる場合があります。
