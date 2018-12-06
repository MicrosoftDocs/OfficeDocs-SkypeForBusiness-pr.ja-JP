---
title: 通話受付管理の有効化
TOCTitle: 通話受付管理の有効化
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48271065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話受付管理の有効化

 

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。CAC ネットワークの構成後、CAC を有効にして、帯域幅制限を強制的に適用する必要があります。この操作の実行には Lync Server コントロール パネルを使用できます。

## Lync Server コントロール パネルから CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**グローバル**\] をクリックします。

4.  \[**グローバル**\] ページで \[**グローバル**\] 構成をクリックします。
    
    > [!NOTE]
    > Microsoft Lync Server 2013 の展開に対して構成できるネットワークは 1 つだけなので、リストに 2 つ以上のネットワーク構成が表示されることはありません。グローバル構成の名前は変更できません。


5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**グローバル設定の編集**\] ページの \[**通話受付管理の有効化**\] チェック ボックスをオンにして、\[**確定**\] をクリックします。

\[**確定**\] をクリックすると、構成のテストが実行されます。 \[**グローバル設定の編集**\] ダイアログ ボックスが閉じ、再び、\[**グローバル**\] ページが表示されます。 ネットワーク構成で、ネットワークの正しい動作を妨げるエラーまたは不整合 (たとえば、すべての地域が他のすべての地域に地域間ルート経由でそれぞれ接続される必要があるがそうなっていない場合) が検出されると、警告が表示されます。

ネットワーク構成に変更を加えた場合は、グローバル構成を開き \[**確定**\] をクリックすることで、検証チェックを再度実行できます。 最初に、CAC を無効にする必要はありません。 チェック ボックスをオンのままにして、\[**確定**\] をクリックしてください。 これは、構成に変更を加えていない場合も含め、いつでも実行できます。

## 関連項目

#### 概念

[Lync Server 2013 通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)  

#### その他のリソース

[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013 での通話管理受付の構成](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

