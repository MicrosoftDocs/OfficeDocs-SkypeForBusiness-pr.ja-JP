---
title: 統合連絡先ストアを使用するための Skype for Business Server の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Exchange Server および Skype for Business Server 用のユニファイド連絡先ストアを構成します。'
ms.openlocfilehash: 1719b8e8e5d99b8ef24da32111b69b1f9f847538
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796998"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>統合連絡先ストアを使用するための Skype for Business Server の構成
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server 用にユニファイド連絡先ストアを構成します。
  
ユニファイド連絡先ストアを使用すると、ユーザーは1つの連絡先リストを保持し、Skype for Business、Microsoft Outlook 2013、Microsoft Outlook Web App 2013 などの複数のアプリケーションでそれらの連絡先を使用できるようになります。 ユーザーに対してユニファイド連絡先ストアを有効にすると、そのユーザーの連絡先は Skype for Business Server に保存されず、必要に応じて取得されます。 代わりに、その連絡先は Exchange Server 2016 または Exchange Server 2013 に保存され、Exchange Web サービスを使用して取得されます。
  
> [!NOTE]
> 技術的には、連絡先情報は、ユーザーの Exchange メールボックスにある一対のフォルダーに格納されます。 連絡先自体は、エンドユーザーに表示される Skype for Business の連絡先という名前のフォルダーに保存されます。連絡先に関するメタデータは、エンドユーザーに表示されないサブフォルダーに格納されます。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

Skype for Business Server と Exchange Server の間のサーバー間認証が既に構成されている場合は、統合連絡先ストアも有効になっています。追加のサーバー構成は必要ありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、ユーザーの連絡先は Skype for Business Server に保存され、統合連絡先ストアには保存されません。
  
統合連絡先ストアへのアクセスは、Skype for Business Server ユーザーサービスポリシーを使って管理されます。 ユーザーサーバーポリシーには、1つのプロパティしかありません (UcsAllowed)。このプロパティは、ユーザーの連絡先が保存されている場所を決定するために使用されます。 ユーザーが、UcsAllowed が True ($True) に設定されているユーザーサービスポリシーによって管理されている場合、ユーザーの連絡先はユニファイド連絡先ストアに保存されます。 ユーザーが、UcsAllowed が False ($False) に設定されているユーザーサービスポリシーによって管理されている場合、そのユーザーの連絡先は Skype for Business Server に保存されます。
  
Skype for Business Server をインストールすると、(グローバルスコープで構成された) 1 つのユーザーサービスポリシーもインストールされます。 このポリシーの UcsAllowed 値は True に設定されていて、ユーザーの連絡先は既定で統合連絡先ストアに格納されます (統合連絡先ストアを展開および構成済みであることが前提です)。 ユーザーの連絡先をすべて統合連絡先ストアに移行したい場合、他の操作を行う必要はありません。 
  
すべての連絡先を統合連絡先ストアに移行しない場合は、すべてのユーザーに対して統合連絡先ストアを無効にできます。その場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定します。
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

グローバルポリシーでユニファイド連絡先ストアを無効にした後は、統合された連絡先ストアの使用を有効にするユーザーごとのポリシーを作成できます。これにより、他のユーザーが引き続き Skype for Business Server に連絡先を保持しながら、一部のユーザーに連絡先を保存しておくことができます。 次のようなコマンドを使用して、ユーザーごとのユーザーサービスポリシーを作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

ポリシーが割り当てられると、Skype for Business Server では、ユーザーの連絡先がユニファイド連絡先ストアに移行されます。 移行が完了すると、ユーザーは Skype for Business Server ではなく Exchange に保存された連絡先になります。 移行が完了した時点でユーザーが Lync 2013 にログオンしている場合は、メッセージボックスが表示され、Skype for Business からログオフするように求められます。その後、プロセスを完了するためにもう一度ログインします。 ユーザーごとのポリシーを割り当てられないユーザーの連絡先は、統合連絡先ストアに移行されません。 これは、これらのユーザーがグローバルポリシーによって管理されており、統合連絡先ストアの使用がグローバルポリシーで無効になっているためです。
  
Skype for Business Server 管理シェル内から[CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps)コマンドレットを実行することで、ユーザーの連絡先が正常に統合された連絡先ストアに移行されたことを確認できます。
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

CsUnifiedContactStore が正常に完了した場合、ユーザー sip: kenmyer@<span></span>litwareinc<span></span>はユニファイド連絡先ストアに移行されたことを意味します。
  
## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

ユーザーの連絡先を、統合された連絡先ストアから削除する必要がある場合 (たとえば、Microsoft Lync Server 2010 上でユーザーがホームポイントを使用する必要があり、そのため、ユニファイド連絡先ストアを使用できなくなった場合) は、2つの操作を行う必要があります。 最初に、ユーザーに、ユニファイド連絡先ストアで連絡先を保存することを禁止する新しいユーザーサービスポリシーを割り当てる必要があります。 (これは、UcsAllowed プロパティが $False に設定されているポリシーです。)このようなポリシーがない場合は、次のようなコマンドを使用して作成できます。
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。
  
> [!NOTE]
> 場合によっては、単純にユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで同じ結果が得られます。 たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。 その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除します。 それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。 以前に割り当てられたユーザーポリシーを割り当て解除するには、前に示したのと同じコマンドを使用しますが、今回は PolicyName パラメーターを null 値に設定します。 Grant-Csuserサービスポリシー-Identity "Ken Myer"-PolicyName $Null 
  
統合連絡先ストアを使用する場合は、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 ユーザーが Skype for Business Server にログオンすると、システムはユーザーのユーザーサービスポリシーをチェックして、ユーザーの連絡先をユニファイド連絡先ストアに保持する必要があるかどうかを確認します。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 回答が「いいえ」の場合、Skype for Business Server はユーザーの連絡先を無視し、次のタスクに進みます。 つまり、Skype for Business Server では、UcsAllowed プロパティの値に関係なく、ユーザーの連絡先が統合された連絡先ストアから自動的に移動されることはありません。
  
つまり、ユーザーに新しいユーザーサービスポリシーを割り当てた後で、 [CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps)コマンドレットを実行して、ユーザーの連絡先を Exchange server から移動して、Skype For business server に戻す必要があります。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

ユーザーサービスのポリシーを変更しても、CsUcsRollback コマンドレットを実行しない場合、Ken の連絡先はユニファイド連絡先ストアから削除されません。 CsUcsRollback を実行しても、Ken Myer のユーザーサービスポリシーを変更しない場合はどうすればよいですか? その場合、Ken の連絡先はユニファイド連絡先ストアから一時的に削除されます。 この削除は一時的なものであるということを念頭に置いておくことが重要です。 Ken の連絡先がユニファイド連絡先ストアから削除されると、Skype for Business Server は7日待ってから、Ken に割り当てられているユーザーサービスポリシーを確認します。 この統合された連絡先ストアのユーザーを有効にするポリシーが Ken に割り当てられている場合、その連絡先は自動的に連絡先ストアに戻されます。 ユニファイド連絡先ストアから連絡先を完全に削除するには、CsUcsRollback コマンドレットを実行するだけでなく、ユーザーサービスのポリシーを変更する必要があります。
  
移行には多くの変数が影響するため、統合連絡先ストアにアカウントが完全に移行されるまでの時間を予想することは困難です。しかし、一般的には、移行が即座に有効になることはありません。移行する連絡先の数が少ない場合でも、完了するまでに 10 分以上かかることもあります。
  

