---
title: 変更会議の Skype ビジネス サーバーの構成設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: を変更する方法を学習する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: 0562758b16418ab79349a27d8eadb509a9f5f6ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884998"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>変更会議の Skype ビジネス サーバーの構成設定
 
**の概要:** 変更する方法を学習 Skype ビジネス サーバーの構成設定に対応します。
  
変更することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>変更ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. 会議構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**会議の構成の編集**] で、構成名以外の構成設定を変更します (構成名は変更不可です)。
    
6. [**確定**] をクリックします。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>変更ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定

会議の構成設定を変更するには、**Set-CsMeetingConfiguration** コマンドレットを使用します。
  
次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議構成設定を変更します。この場合、DesignateAsPresenter プロパティの値が "Everyone" に設定されています。
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

詳細については、パラメーターの一覧を含む[セット CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)を参照してください。
  

