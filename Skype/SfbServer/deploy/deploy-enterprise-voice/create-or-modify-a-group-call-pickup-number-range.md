---
title: Skype for Business のグループ通話集配の番号範囲を作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Skype for Business Server Enterprise Voice でグループ通話の集配番号の範囲を作成または変更します。
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767880"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Skype for Business のグループ通話集配の番号範囲を作成または変更する

Skype for Business Server Enterprise Voice でグループ通話の集配番号の範囲を作成または変更します。

グループ通話のピックアップは、コールパークアプリケーションに基づいています。 グループ通話の集配を展開するときに、通話集配グループ番号として指定されている電話番号の範囲を使って、コールパークの軌道テーブルを構成する必要があります。 ユーザーはこのグループ番号にダイヤルし、他のユーザーに着信している通話をピックアップします。

コール パーク オービットの番号と同様に、通話ピックアップのグループ番号には、ユーザーや電話が割り当てられていない仮想の内線番号を使用する必要があります。 グループ通話のピックアップを展開する各フロントエンドプールには、1つ以上の通話ピックアップグループ番号が含まれていることがあります。 このグループ番号範囲は、展開全体でグローバルに一意である必要があり、**GroupPickup** の種類として割り当てることも必要です。

次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。

> [!NOTE]
> 通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Skype for Business Server 管理シェルを使用する必要があります。 グループ通話の集配番号範囲は、Skype for Business Server コントロールパネルでは使用できません。

通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。

- 範囲の開始番号が終了番号より大きくならないようにしてください。

- 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

- 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

- 数値の範囲が文字\*または # で始まる場合、範囲は100よりも大きくなければなりません。

- 有効な値: 正規表現文字列と一致する必要\\があります ([* | #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8}) つまり、文字\*または # のいずれかから始まる文字列、または 1 ~ 9 の数値 (最初の文字はゼロにすることはできません) であることを意味します。 最初の文字が\*または # の場合、次の文字は 1 ~ 9 の数字にする必要があります (0 にすることはできません)。 後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば、"#6000"\*、"92000"\*、"95551212"、"915551212")。 最初の文字が "not \* " または "#" である場合、最初の文字は 1 ~ 9 の数字 (0 にすることはできません)、数字 0 ~ 9 (たとえば、"915551212"、"41212"、"300") でなければなりません。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップ グループの範囲を作成するには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. 通話ピックアップ グループ番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。 通話ピックアップ番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。

    コマンド ラインで、次のコマンドを実行します。

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。 番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。 たとえば、番号の範囲を [CallPark] から [GroupPick] に変更すると、その範囲の orbits を使用して通話をパークすることができなくなります。

## <a name="see-also"></a>関連項目

[新規-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コールパークの範囲を削除する](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
