---
title: 'Lync Server 2013: ユーザーに対するコール パークの有効化'
TOCTitle: ユーザーに対するコール パークの有効化
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48272912
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザーに対するコール パークの有効化

 

_**トピックの最終更新日:** 2012-09-11_

ユーザーは、音声ポリシーで コール パークを有効にするまで通話の保留や保留された通話の取得はできません。

> [!NOTE]
> 既定では、 コール パークはすべてのユーザーに対して無効になっています。


コール パークは、グローバル スコープ、サイト スコープ、またはユーザー スコープで有効にできます。ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。複数の音声ポリシーがある場合、グローバル ポリシーだけでなく、 コール パークを有効にするすべてのポリシーを確認してください。

## Lync Server コントロール パネルを使用してユーザーの コール パークを有効にするには

1.  **RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、 **CsVoiceAdministrator**、 **CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックします。

4.  \[**音声ポリシー**\] タブをクリックします。

5.  既存の音声ポリシーをダブルクリックして、\[**音声ポリシーの編集**\] ダイアログ ボックスを開きます。

6.  \[**通話機能**\] の \[**コール パークを有効にする**\] を選択します。

7.  \[**OK**\] をクリックして音声ポリシーを保存します。

## コマンドレットを使用してユーザーの コール パークを有効にするには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    たとえば、既定のグローバル音声ポリシーの コール パークを有効にする場合は次のようになります。
    
        Set-CsVoicePolicy -EnableCallPark $true

## 関連項目

#### タスク

[Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

