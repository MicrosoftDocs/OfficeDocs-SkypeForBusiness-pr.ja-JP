---
title: 統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成
TOCTitle: 統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49886991
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成

 

_**トピックの最終更新日:** 2014-02-07_

統合連絡先ストアを使用すると、ユーザーは単一の連絡先リストを保持し、その連絡先を Microsoft Lync 2013、Microsoft Outlook 2013、Microsoft Outlook Web App 2013 などの複数のアプリケーションで使用することができます。ユーザーに対して統合連絡先ストアを有効にすると、そのユーザーの連絡先は Microsoft Lync Server 2013 に格納されて SIP プロトコルを使用して取得されるのではなく、Microsoft Exchange Server 2013 に格納されて Exchange Web サービスを使用して取得されるようになります。

> [!NOTE]
> 技術的には、連絡先情報はユーザーの Exchange 2013 メールボックスにある 1 組のフォルダーに格納されます。連絡先自体は、エンド ユーザーに表示される &quot;Lync 連絡先&quot; という名前のフォルダーに格納され、連絡先に関するメタデータは、エンド ユーザーには表示されないサブフォルダーに格納されます。


## ユーザーに対して統合連絡先ストアを有効にする

Lync Server 2013 と Exchange 2013 の間のサーバー間認証を既に構成している場合は、統合連絡先ストアの使用も有効にされているため、追加のサーバー構成を行う必要はありません。ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。既定では、ユーザーの連絡先は Lync Server に保存され、統合連絡先ストアには保存されません。

統合連絡先ストアへのアクセスは、Lync Server のユーザー サービス ポリシーを使用して管理されます。ユーザー サービス ポリシーには 1 つのプロパティ (UcsAllowed) しかありません。このプロパティは、ユーザーの連絡先の格納場所を決定するために使用されます。UcsAllowed が True ($True) に設定されたユーザー サービス ポリシーによってユーザーが管理されている場合、そのユーザーの連絡先は統合連絡先ストアに格納されます。UcsAllowed が False ($False) に設定されたユーザー サービス ポリシーによってユーザーが管理されている場合、そのユーザーの連絡先は Lync Server に格納されます。

Lync Server 2013 をインストールすると、(グローバル スコープで構成された) 単一のユーザー サービス ポリシーもインストールされます。このポリシーの UcsAllowed 値は True に設定されていて、既定によって、ユーザーの連絡先は統合連絡先ストアに格納されます。ユーザーの連絡先をすべて統合連絡先ストアに移行したい場合、他の操作を行う必要はありません。

すべての連絡先を統合連絡先ストアに移行しない場合は、すべてのユーザーに対して統合連絡先ストアを無効にできます。その場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定します。

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

グローバル ポリシーによって統合連絡先ストアを無効にした後で、統合連絡先ストアの使用を有効にするユーザーごとのポリシーを作成することもできます。これにより、一部のユーザーの連絡先を統合連絡先ストアに保存し、他のユーザーの連絡先を引き続き Lync Server に保存することが可能になります。ユーザーごとのユーザー サービス ポリシーは、次のようなコマンドを使用して作成できます。

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

ポリシーの割り当てが完了すると、Lync Server は統合連絡先ストアへのユーザーの連絡先の移行を開始します。移行後は、ユーザーの連絡先が Lync Server ではなく Exchange に格納されます。移行の完了時にユーザーが Lync 2013 にログオンしている場合は、メッセージ ボックスが表示され、プロセスを完了するために Lync からログオフして再度ログオンするように求められます。ユーザーごとのポリシーを割り当てられないユーザーの連絡先は、統合連絡先ストアに移行されません。そのようなユーザーはグローバル ポリシーで管理され、グローバル ポリシーでは統合連絡先ストアの使用が無効になっているためです。

ユーザーの連絡先が統合連絡先ストアに正常に移行されたことを確認するには、Lync Server 管理シェルから [Test-CsUnifiedContactStore](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUnifiedContactStore) コマンドレットを実行します。

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Test-CsUnifiedContactStore が成功すれば、統合連絡先ストアへのユーザー sip:kenmyer@litwareinc.com の連絡先の移行は完了しています。

## 統合連絡先ストアのロールバック

統合連絡先ストアからユーザーの連絡先を削除する必要がある場合 (たとえば、ユーザーの所属先を Microsoft Lync Server 2010 に変更する必要があり、ユーザーが統合連絡先ストアを使用できなくなった場合など)、2 つの操作を行う必要があります。まず、統合連絡先ストアへの連絡先の格納を禁止する新しいユーザー サービス ポリシー (つまり、UcsAllowed プロパティが $False に設定されたポリシー) をユーザーに割り当てる必要があります。そのようなポリシーがない場合、次のようなコマンドを使用して作成できます。

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。

> [!NOTE]  
> 場合によっては、単純にユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで同じ結果が得られます。たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除します。それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。<br />
> 以前に割り当てたユーザーごとのポリシーを割り当て解除するには、上記と同じコマンドを使用しますが、PolicyName パラメーターを null 値に設定します。<br />
> Grant-CsUserServicesPolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null


統合連絡先ストアを操作する際には、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。ユーザーが Lync Server 2013 にログオンする際に、システムはユーザーのユーザー サービス ポリシーをチェックして、そのユーザーの連絡先を統合連絡先ストアに保存する必要があるかどうかを調べます。答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。答えが「いいえ」である場合は、Lync Server は単にユーザーの連絡先を無視し、次のタスクに移行します。つまり、UcsAllowed プロパティの値にかかわらず、Lync Server がユーザーの連絡先を統合連絡先ストアから自動的に移動することはありません。

また、ユーザーの連絡先を Exchange 2013 から Lync Server 2013 に戻すためには、新しいユーザー サービス ポリシーをユーザーに割り当てた後で [Invoke-CsUcsRollback](https://docs.microsoft.com/en-us/powershell/module/skype/Invoke-CsUcsRollback) コマンドレットを実行する必要があります。たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。

    Invoke-CsUcsRollback -Identity "Ken Myer"

ユーザー サービス ポリシーを変更して Invoke-CsUcsRollback コマンドレットを実行しない場合、Ken の連絡先は統合連絡先ストアから削除されません。Invoke-CsUcsRollback を実行して Ken Myer のユーザー サービス ポリシーを変更しない場合は、Ken の連絡先が統合連絡先ストアから一時的に削除されます。この削除は一時的であるという点が重要です。Ken の連絡先が統合連絡先ストアから削除されると、Lync Server 2013 は 7 日間待機した後、Ken に割り当てられているユーザー サービス ポリシーを調べます。統合連絡先ストアの使用を有効にするポリシーが引き続き Ken に割り当てられている場合、Ken の連絡先は自動的に連絡先ストアに戻されます。統合連絡先ストアから連絡先を完全に削除するには、Invoke-CsUcsRollback コマンドレットを実行するだけでなく、ユーザー サービス ポリシーも変更する必要があります。

移行には多くの変数が影響するため、統合連絡先ストアにアカウントが完全に移行されるまでの時間を予想することは困難です。しかし、一般的には、移行が即座に有効になることはありません。移行する連絡先の数が少ない場合でも、完了するまでに 10 分以上かかることもあります。

