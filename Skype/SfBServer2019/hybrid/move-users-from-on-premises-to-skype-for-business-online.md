---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Skype をビジネス オンラインのユーザーを移動する方法について説明します。
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243998"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>ユーザーをオンプレミスから Skype for Business Online に移動する

移動した後、ユーザー設置から Skype オンライン ビジネスのユーザーと対話する Skype オンライン ビジネスの機能をします。 設置型に存在していた取引先担当者は、ビジネス オンラインの Skype で利用可能ななりビジネス オンラインの Skype のリンクをポイントするように将来のユーザーが構成されて、既存の会議の更新されます。 オーディオ会議で、ユーザーが有効な場合、会議はダイヤルインの座標も含まれます。  ビジネス オンラインの Skype をオンプレミス環境からユーザーを移動するには、設置型のツールは、両方とも、ビジネス サーバー コントロール パネルの移動 CsUser コマンドレット、または、Skype のいずれかを使用します。 

すべてのユーザーを移動する前に必ずユーザーをクラウドに移行する[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。
 
## <a name="move-users-with-move-csuser"></a>Csuser からの移動でユーザーの移動 

Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。 [管理者の資格情報が必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明したように両方設置環境にも、Office 365 テナントのように十分な特権が必要です。 両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。

オンラインにユーザーを移動する移動 CsUser を使用します。

- Id パラメーターを使用して移動するユーザーを指定します。
- 指定ターゲット パラメーターを指定する値"sipfed.online.lync。<span>com"します。
- 設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、Office 365 のための十分な権限を持つアカウントを指定するには、資格情報パラメーターです。
- 」On.microsoft で Office 365 にアクセス許可を持つアカウントが終わっていない場合。<span>com」、[ために必要な管理者資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明するよう、正しい値を持つ、- HostedMigrationOverrideUrl パラメーターを指定する必要があり、。

次のコマンドレットのシーケンスは、Skype をビジネス オンラインでのユーザーを移動する使用することができ、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype でユーザーを移動します。 

1. ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。
2. 左側のナビゲーションでは、**ユーザー**を選択します。
3. **検索**を使用すると、Skype のビジネスをオンラインに移動したいユーザーを検索できます。
4. 、ユーザーを選択して、**アクション**ドロップダウン リストの上からクリックして**Skype オンライン ビジネス用に選択したユーザーを移動**します。
5. ウィザードで、[**次へ**] クリックします。
6. メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。
7. ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。
8. ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。

## <a name="see-also"></a>関連項目

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)