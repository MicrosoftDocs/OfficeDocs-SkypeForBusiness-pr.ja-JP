---
title: 通話受付管理の有効化
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
description: " 通話受付管理 (CAC) ネットワークを構成した後、CAC を有効にして帯域幅の制限を適用する必要があります。"
ms.openlocfilehash: 090b19282ce85289b0e79e09d58646c5bf5e81e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118576"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server での通話受付管理の有効化

通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。 CAC ネットワークの構成後、CAC を有効にして、帯域幅制限を強制的に適用する必要があります。 これを行うには、Skype for Business Server コントロール パネルを使用できます。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルから CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[グローバル] を **クリックします**。

4.  [**グローバル**] ページで [**グローバル**] 構成をクリックします。
   
    > [!NOTE]  
    > Skype for Business Server 展開に対して構成できるネットワークは 1 つのみです。そのため、一覧に複数のネットワーク構成が含めらなさる必要があります。 グローバル構成の名前は変更できません。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにして、[**確定**] をクリックします。

[**確定**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログ ボックスが閉じ、再び、[**グローバル**] ページが表示されます。 ネットワーク構成で、ネットワークの正しい動作を妨げるエラーまたは不整合 (たとえば、すべての地域が他のすべての地域に地域間ルート経由でそれぞれ接続される必要があるがそうなっていない場合) が検出されると、警告が表示されます。

ネットワーク構成に変更を加えた場合は、グローバル構成を開き [**確定**] をクリックすることで、検証チェックを再度実行できます。 最初に、CAC を無効にする必要はありません。 チェック ボックスをオンのままにして、[**確定**] をクリックしてください。 これは、構成に変更を加えていない場合も含め、いつでも実行できます。

## <a name="see-also"></a>関連項目

[通話受付管理の計画](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[通話受付管理の展開](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](/powershell/module/skype/Remove-CsNetworkConfiguration)