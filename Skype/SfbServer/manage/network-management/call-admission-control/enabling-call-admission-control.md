---
title: 通話受付制御の有効化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " 通話受付制御 (CAC) ネットワークを構成した後、帯域幅の制限を適用するために、CAC を有効にする必要があります。"
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817536"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server での通話受付管理の有効化

通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。 CAC ネットワークを構成したら、CAC を有効にして帯域幅の制限を適用する必要があります。 この操作には、Skype for Business Server コントロールパネルを使うことができます。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルから CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで、[**グローバル**構成] をクリックします。
   
    > [!NOTE]  
    > 任意の Skype for Business Server の展開用に1つのネットワークのみを構成できます。そのため、リストには複数のネットワーク構成を設定することはできません。 グローバル構成の名前を変更することはできません。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページで、[**通話受付制御を有効にする**] チェックボックスをオンにし、[**コミット**] をクリックします。

[**コミット**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログボックスが閉じ、**グローバル**ページに戻ります。 ネットワーク構成でエラーや不整合が検出された場合、そのエラーや不整合が正常に動作しなくなる場合 (たとえば、すべての地域が相互に接続されているルートを介してすべての地域に接続されていない場合) は、警告が表示されます。

ネットワーク構成を変更した場合は、[グローバル構成] を開き、[**コミット**] をクリックして、検証チェックをもう一度実行できます。 まず、CAC を無効にする必要はありません。チェックボックスをオンのままにして、[**コミット**] をクリックします。 この操作は、構成を変更することなくいつでも行うことができます。

## <a name="see-also"></a>関連項目

[通話受付管理の計画](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[通話受付管理の展開](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
