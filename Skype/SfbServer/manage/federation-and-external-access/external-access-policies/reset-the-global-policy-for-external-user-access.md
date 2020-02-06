---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: グローバルポリシーを完全に削除することはできません。 グローバルポリシーの [**削除**] オプションを使うと、グローバルポリシーは既定の設定にリセットされます。これには、外部ユーザーアクセスオプションのサポートは含まれません。
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818268"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Skype for Business Server で外部ユーザーアクセスのグローバルポリシーをリセットする 

使用しない外部ユーザーアクセスポリシーを作成または構成している場合は、次の操作を行うことができます。

  - 作成したサイトまたはユーザーのポリシーを削除します。

  - グローバルポリシーを既定の設定にリセットします。 既定のグローバルポリシー設定では、外部ユーザーのアクセスを拒否します。 グローバルポリシーは削除できません。

グローバルポリシーを完全に削除することはできません。 グローバルポリシーの [**削除**] オプションを使うと、グローバルポリシーは既定の設定にリセットされます。これには、外部ユーザーアクセスオプションのサポートは含まれません。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバルポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**]、[**外部アクセスポリシー**] の順番にクリックします。

4.  [**外部アクセスポリシー** ] タブで、グローバルポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。 ページの上部に、グローバルポリシーがリセットされたことを通知するメッセージが表示されます。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してグローバル外部アクセスポリシーをリセットする

グローバル外部アクセスポリシーをリセットするには、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはリモートセッション Windows PowerShell から実行できます。 

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセスポリシーをリセットするには

  - このコマンドは、グローバル外部アクセスポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。


