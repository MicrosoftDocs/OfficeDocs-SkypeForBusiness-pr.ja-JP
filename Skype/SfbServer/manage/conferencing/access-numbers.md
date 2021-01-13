---
title: 'Skype for Business Server でダイヤルイン会議アクセス番号を管理する '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '概要: Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。'
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806487"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議アクセス番号を管理する
 
**概要:** Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。
  
ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。 
  
このトピックでは、既存のダイヤルイン会議アクセス番号を表示、変更、または削除する方法について説明します。 最初のダイヤルイン アクセス番号を作成する方法の詳細については、「Skype for Business Server でダイヤルイン会議を構成する [」を参照してください](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>ダイヤルイン会議アクセス番号の表示

ダイヤルイン会議アクセス番号は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して表示できます。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してダイヤルイン アクセス番号を表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス番号**] ページで、表示するアクセス番号をクリックします。
    
5. [ **編集] で**、[詳細の表示 **] チェック ボックス** をオンにします。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルイン アクセス番号を表示する

ダイヤルイン アクセス番号に関する情報を表示するには **、Get-CsDialInConferencingAccessNumber コマンドレットを使用** します。
  
次のコマンドは、組織で使用するように構成された、すべてのダイヤルイン会議アクセス番号のコレクションを戻します。 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

返される情報の種類の例を次に示します。
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>ダイヤルイン会議アクセス番号を変更する

ダイヤルイン アクセス番号は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してダイヤルイン アクセス番号を変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス** 番号] ページで、一覧のダイヤルイン アクセス番号の 1つをクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。
    
    > [!NOTE]
    > 検索フィールドを使用してダイヤルイン アクセス番号のリスト内の列の内容を検索すると、期待した結果が得られるとは言えな場合があります。 代わりに、関心のある列で一覧を並べ替え、表示または変更するダイヤルイン アクセス番号を識別します。 
  
5. [ **表示番号]** に、公衆交換電話網 (PSTN) 電話ユーザーが電話会議に参加するためにダイヤルする電話番号を入力します。 
    
    この番号は、会議出席依頼とダイヤルイン会議の設定 Web ページに表示されます。
    
6. [ **表示名]** に、ダイヤルイン アクセス番号の説明を入力します。 これは、Skype for Business 検索結果のダイヤルイン アクセス番号に関連付けられている名前です。
    
    この名前は、ユーザーがアクセス番号を呼び出す際にクライアントに表示されます。 
    
7. [ **回線 URI]** で、ダイヤルイン アクセス番号の E.164 番号を TEL URI 形式で入力します。この番号の前に +記号を付け、スペースを除きます。 たとえば、tel:+14255550200 などです。
    
    > [!NOTE]
    > 同じ回線 URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. **SIP URI で、** 次の操作を行います。
    
   テキスト ボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI は、通話通知メッセージや以前のバージョンの Lync クライアントなど、さまざまな場所に表示されます。
    
    > [!NOTE]
    > 同じ SIP URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 SIP URI は、アクセス番号の作成後に変更できません。 SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成する方法です。 
  
   ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議アテンダント アプリケーションのドメインをクリックします。
    
9. [ **プール]** で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は **、Move-CsApplicationEndpoint** コマンドレットを使用するか、アクセス番号を削除して再作成する必要があります。
  
10. 第 **1 言語** で、このダイヤルイン アクセス番号のプロンプトが再生される言語をクリックします。 
    
    第 1 言語は、会議アテンダントが通話に応答するために使用する言語です。 サポートされている言語は、ダイヤルイン会議の設定 Web ページに各アクセス電話番号と共に表示されます。
    
11. (省略可能)第 **2** 言語 (最大 4つ) で、[追加] をクリックし、このダイヤルイン アクセス番号の発信者に対してサポートする追加の言語を 1 つ以上選択し **、[OK]** をクリックします。 
    
    ダイヤルイン アクセス番号ごとに、最大 4 つの第 2 言語を選択できます。 ユーザーは、会議にダイヤルインするときに会議 ID を入力する前に第 2 言語を選択できます。
    
12. ダイヤルイン アクセス番号の地域を追加するには、[関連付けられた地域] で[追加] をクリックし、このダイヤルイン アクセス番号のダイヤル プランに関連付けられている 1 つ以上の地域をクリックして **、[OK]** をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[関連付けられている地域] で、削除する地域をクリックし、[削除] をクリック **します**。
    
14. [**確定**] をクリックします。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルイン アクセス番号を変更する

ダイヤルイン アクセス番号を変更するには **、Set-CsDialInConferencingAccessNumber コマンドレットを使用** します。
  
次のコマンドは、ID が設定されたダイヤルイン会議アクセス番号の DisplayName プロパティをsip:RedmondDialIn@litwareinc.com。 この例では、表示名が "Redmond Dial-In Access Number" に設定されています。
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

次の例では、Id が sip:RedmondDialIn@litwareinc.com のダイヤルイン会議アクセス番号を変更して、Redmond と Seattle の 2 つの地域が含まれます。 これを行うため、Region パラメーターを呼び出して、その後に 2 つの地域 (コンマで区切られた 2 つの文字列値) を指定します。 このコマンドは、Redmond および Seattle の両地域がダイヤル プランで既に定義されていないと失敗します。
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

詳細については [、「Set-CsDialInConferencingAccessNumber」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>ダイヤルイン会議アクセス番号を削除する

ダイヤルイン会議アクセス番号は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して削除できます。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してダイヤルイン会議アクセス番号を削除する

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**OK**] をクリックします。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルイン会議アクセス番号を削除する

ダイヤルイン会議アクセス番号を削除するには **、Remove-CsDialInConferencingAccessNumber を使用します**。
  
次のコマンドは、ID が設定されたダイヤルイン会議アクセス番号を削除sip:RedmondDialInAccess@litwareinc.com。
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

次のコマンドは、Northwest 地域に関連付けられているすべてのダイヤルイン会議アクセス番号を削除します。
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

次のコマンドは、イタリア語が第 1 言語であるすべてのダイヤルイン会議アクセス番号を削除します。
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

詳細については [、「Remove-CsDialInConferencingAccessNumber」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。
  

