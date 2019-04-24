---
title: 統合連絡先ストアを使用するための Skype for Business Server の構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: '概要: ビジネスのサーバーの Exchange Server と Skype の統合連絡先ストアを構成します。'
ms.openlocfilehash: fd58c0cfd86092bb1a6004ac4d70c98c51062ea1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216614"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>統合連絡先ストアを使用するための Skype for Business Server の構成
 
**の概要:** 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバーの統合連絡先ストアを構成します。
  
統合連絡先ストアを使用すると、ユーザー 1 つの連絡先リストを維持し、ビジネス、Microsoft Outlook 2013 では、Microsoft Outlook Web App の 2013 の Skype を含めて、複数のアプリケーションで使用可能な連絡先です。 ユーザーは、ユーザーの連絡先がないビジネス サーバーの Skype で保存され、必要に応じてを取得、統合連絡先ストアを有効にすると、します。 代わりに、自分の連絡先では、2016 の Exchange Server や Exchange Server 2013 に格納され、Exchange Web サービスを使用して取得します。
  
> [!NOTE]
> 技術的には、連絡先情報は、1 組のユーザーの Exchange メールボックス内のフォルダーに格納されます。 自身の連絡先が Skype エンド ・ ユーザーに表示されるビジネス用連絡先の名前が付いたフォルダーに格納されています。連絡先についてのメタデータは、エンド ・ ユーザーに表示されていないサブフォルダーに格納されます。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

Skype ビジネス サーバーと Exchange Server 間でサーバーからサーバーへの認証が既に構成されている場合、また有効にしている統合連絡先ストアです。追加のサーバーを構成する必要はありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、Skype のビジネス サーバーでは統合連絡先ストアではなくユーザーの連絡先が保持されます。
  
統合連絡先ストアへのアクセスは、Skype を使用してビジネス サーバー ユーザー サービス ポリシーによって管理されます。 ユーザーのサーバーのポリシーがあるだけ、1 つのプロパティ (UcsAllowed)。ユーザーの連絡先が格納される場所を決定するのにはこのプロパティを使用します。 UcsAllowed が True ($True) に設定されているユーザー サービス ポリシーによって、ユーザーが管理されている場合は、統合連絡先ストアにユーザーの連絡先が保存されます。 によって、ユーザーが管理されている場合、ユーザーは、UcsAllowed が False ($False) に設定されているし、[自分の連絡先は Skype ビジネス サーバー用のポリシーをサービスします。
  
ビジネス サーバーの Skype をインストールすると、1 つのユーザー サービス ポリシー (グローバル スコープで構成されている) もインストールされます。 このポリシーの UcsAllowed 値は True に設定されていて、ユーザーの連絡先は既定で統合連絡先ストアに格納されます (統合連絡先ストアを展開および構成済みであることが前提です)。 ユーザーの連絡先をすべて統合連絡先ストアに移行したい場合、他の操作を行う必要はありません。 
  
すべての連絡先を統合連絡先ストアに移行しない場合は、すべてのユーザーに対して統合連絡先ストアを無効にできます。その場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定します。
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

グローバル ポリシーの統合連絡先ストアを無効にした後、作成、統合連絡先ストアの使用を有効にするユーザーごとのポリシーこれにより、いくつかのユーザーにビジネス サーバー Skype で自分の連絡先を保持するように他のユーザーを処理しながら、統合連絡先ストアに、連絡先を保持することができます。 次のようなコマンドを使用して、ユーザーごとのユーザー サービス ポリシーを作成できます。
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

ポリシーが割り当てられると、ユーザーの連絡先を統合連絡先ストアに移行する Skype のビジネス サーバーが開始されます。 移行が完了した後、ユーザーがビジネスのサーバーの Skype ではなく Exchange に格納されて、自分の連絡先。 上にログを記録する場合は、ユーザー時間移行の Lync 2013 が完了するとメッセージ ボックスが表示されます、彼または彼女にビジネス用の Skype からログオフし、再度ログオン プロセスを終了するために求められます。 ユーザーごとのポリシーを割り当てられないユーザーの連絡先は、統合連絡先ストアに移行されません。 それらのユーザーは、グローバル ポリシーによって管理されているが、統合連絡先ストアの使用がグローバル ポリシーで無効になっているためにです。
  
ユーザーの連絡先があるコマンドレットを実行して、[テスト CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps)から、Skype のビジネス サーバー管理シェルの統合連絡先ストアに正常に移行されたことを確認することができます。
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

テスト CsUnifiedContactStore は成功した場合ことを意味、連絡先、ユーザー sip: kenmyer の @<span></span>litwareinc<span></span>.com 統合連絡先ストアに移行します。
  
## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

(たとえば、場合、ユーザーは Microsoft Lync Server 2010 のホーム サーバーを変更する必要があるし、このように統合連絡先ストアを使用できなく) は、統合連絡先ストアからユーザーの連絡先を削除する必要がある場合は、2 つの操作を行う必要があります。 最初に、いずれかの連絡先を統合連絡先ストアに格納することは禁止されていますが、新規のユーザー サービス ポリシーが、ユーザーを割り当てる必要があります。 (つまり、ポリシー、UcsAllowed プロパティを持つされて $False に設定します。)このようなポリシーがない場合は、次のようなコマンドを使用して 1 つを作成できます。
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。
  
> [!NOTE]
> 場合によっては、単純にユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで同じ結果が得られます。 たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。 その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除します。 それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。 割り当ての解除、以前に割り当てられたユーザーごとのポリシーにする前のように同じコマンドを使用するが、今度はグループ パラメーターを null 値に設定する: 補助金 CsUserServicesPolicy ・ アイデンティティ"Ken Myer"グループ $Null 
  
統合連絡先ストアを使用する場合は、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 Skype ビジネス サーバー用にユーザーがログオン、システムは統合連絡先ストアに自分の連絡先を保持するかどうかを確認するユーザーのユーザー サービスのポリシーをチェックします。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 回答した場合は残念ですが、Skype ビジネス サーバーの単にユーザーの連絡先を無視し、上の次のタスクを移動します。 つまり、Skype ビジネス サーバーに自動的には移動しませんユーザーの連絡先 UcsAllowed プロパティの値に関係なく、統合連絡先ストアからです。
  
、ユーザーの新しいユーザー サービス ポリシーを割り当て、後実行すること必要がありますし、[呼び出し CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps)コマンドレット ビジネス サーバーの Exchange Server が、Skype のユーザーの連絡先を移動するためにすることも意味します。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

ユーザー サービス ポリシーを変更する場合は実行しない呼び出し CsUcsRollback コマンドレット Ken の連絡先は、統合連絡先ストアからは削除されません。 場合呼び出し CsUcsRollback を実行するが、Ken Myer のユーザー サービス ポリシーを変更できないでしょうか。 その場合は、統合連絡先ストアから Ken の連絡先を一時的に削除されます。 この削除は一時的なことが念頭においてください。 Ken の連絡先は、統合連絡先ストアから削除されたが後、Skype ビジネス サーバーの 7 日間の待機、ユーザー サービス ポリシーを Ken に割り当てられているを確認します。 Ken には、統合連絡先ストアのユーザーを有効にするポリシーが割り当てられたままな場合、彼の連絡先は自動的に再び移動の連絡先に保存します。 統合連絡先ストアから連絡先を完全に削除するのには呼び出し CsUcsRollback コマンドレットを実行するだけでなく、ユーザー サービス ポリシーを変更する必要があります。
  
移行には多くの変数が影響するため、統合連絡先ストアにアカウントが完全に移行されるまでの時間を予想することは困難です。しかし、一般的には、移行が即座に有効になることはありません。移行する連絡先の数が少ない場合でも、完了するまでに 10 分以上かかることもあります。
  

