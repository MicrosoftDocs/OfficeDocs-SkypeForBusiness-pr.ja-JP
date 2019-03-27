---
title: 呼受付制御を有効にします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 呼び出し受付制御 (CAC) ネットワークを構成すると、CAC 帯域幅の制限を適用するを有効にする必要があります。"
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897644"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server での通話受付管理の有効化

通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。 CAC ネットワークを構成した後は、CAC 帯域幅の制限を適用するを有効にする必要があります。 ビジネス サーバーのコントロール パネルの Skype を使用するにはこれを行う。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype から CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで、[**グローバル**構成] をクリックします。
   
    > [!NOTE]  
    > 決してあるため、ボックスの一覧で複数のネットワーク構成、ビジネスのサーバー展開では、すべての Skype の 1 つだけのネットワークを構成できます。 グローバル構成の名前を変更することはできません。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  **グローバル設定の編集**] ページで [**呼受付制御の有効にする**] チェック ボックスを選択し、[**コミット**] をクリックします。

**コミット**] をクリックすると、構成のテストを実行します。 **グローバル**のページに戻る場合、**グローバル設定の編集**] ダイアログ ボックスを閉じます。 (たとえば、interregion のルートを他のすべての領域には、すべての領域は接続されていない) 場合に正常に動作しない可能性が、ネットワーク構成では、エラーまたは不整合が検出された場合、警告が表示されます。

ネットワーク構成に変更を加えた場合は、グローバル構成を開き、**コミット**をクリックすると検証チェックをもう一度を実行できます。 最初の CAC を無効にする必要はありません: チェック ボックスをオンのままにし、[**コミット**] をクリックします。 この設定は、構成変更を加えずにいつでも行うことができます。

## <a name="see-also"></a>関連項目

[通話受付管理の計画](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[通話受付管理の展開](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[セット CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[削除 CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
