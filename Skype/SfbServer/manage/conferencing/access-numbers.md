---
title: 'Skype for Business Server でダイヤルイン会議アクセス番号を管理する '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '概要: Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。'
ms.openlocfilehash: e41011c4ba06da7f05d8cb1a52717e707cd2f8bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289035"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議アクセス番号を管理する
 
**概要:** Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。
  
ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。 
  
このトピックでは、既存のダイヤルイン会議アクセス番号を表示、変更、または削除する方法について説明します。 最初のダイヤルインアクセス番号の作成方法の詳細については、「 [Skype For Business Server でダイヤルイン会議を構成](../../deploy/deploy-conferencing/dial-in-conferencing.md)する」を参照してください。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>ダイヤルイン会議アクセス番号の表示

Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を表示することができます。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号を表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス番号**] ページで、表示するアクセス番号をクリックします。
    
5. [**編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を表示する

ダイヤルイン アクセス番号に関する情報を表示するには、**Get-CsDialInConferencingAccessNumber** コマンドレットを使用します。
  
次のコマンドは、組織で使用できるように構成されているすべてのダイヤルイン会議アクセス番号のコレクションを返します。 
  
```
Get-CsDialInConferencingAccessNumber
```

次に、戻される情報の種類に関する例を示します。
  
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

詳細については、「 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>ダイヤルイン会議アクセス番号の変更

Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を変更できます。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号を変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス番号**] ページで、リスト内にあるダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
    > [!NOTE]
    > 検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。 
  
5. [**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。 
    
    この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。
    
6. [**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。 これは、Skype for Business の検索結果のダイヤルインアクセス番号と関連付けられた名前です。
    
    この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。 
    
7. [**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。
    
    > [!NOTE]
    > 同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. [**SIP URI**] で、次の操作を行ってください。
    
   テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI は、通話通知メッセージや以前のバージョンの Lync クライアントのように、さまざまな場所に表示されます。
    
    > [!NOTE]
    > 同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。 
  
   ドロップダウンリストボックスで、ダイヤルインアクセス番号をサポートする会議アテンダントアプリケーションのドメインをクリックします。
    
9. [**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は、**Move-CsApplicationEndpoint** コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。
  
10. [**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。 
    
    第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。
    
11. (オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。 
    
    ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。
    
12. ダイヤルインアクセス番号の領域を追加するには、[**関連付けられた地域**] の [**追加**] をクリックし、このダイヤルインアクセス番号のダイヤルプランに関連付けられている1つ以上の領域をクリックして、[ **OK]** をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。
    
14. [**確定**] をクリックします。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を変更する

ダイヤルイン アクセス番号を変更するには、**Set-CsDialInConferencingAccessNumber** コマンドレットを使用します。
  
次のコマンドにより、Identity が sip:RedmondDialIn@litwareinc.com になっているダイヤルイン会議アクセス番号の DisplayName プロパティが変更されます。この例では、表示名が「Redmond Dial-In Access Number」に設定されます。
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

次の例では、sip:RedmondDialIn@litwareinc.com という ID を持つダイヤルイン会議アクセス番号が 2 つの地域 (Redmond および Seattle) を含むように変更します。これを行うため、Region パラメーターを呼び出して、その後に 2 つの地域 (コンマで区切られた 2 つの文字列値) を指定します。このコマンドは、Redmond および Seattle の両地域がダイヤル プランで既に定義されていないと失敗します。
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

詳細については、「 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>ダイヤルイン会議アクセス番号の削除

Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を削除できます。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルイン会議アクセス番号を削除する

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**OK**] をクリックします。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を削除する

ダイヤルイン会議アクセス番号を削除するには、**Remove-CsDialInConferencingAccessNumber** を使用します。
  
次のコマンドは、ID が sip:RedmondDialInAccess@litwareinc.com であるダイヤルイン会議アクセス番号を削除します。
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

次のコマンドは、Northwest 地域に関連するすべてのダイヤルイン会議アクセス番号を削除します。
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

次のコマンドは、第 1 言語がイタリア語であるすべてのダイヤルイン会議アクセス番号を削除します。
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

詳細については、「 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。
  

