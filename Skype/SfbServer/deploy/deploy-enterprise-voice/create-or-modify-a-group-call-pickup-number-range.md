---
title: Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Create or modify a Group Call Pickup number range in Skype for Business Server エンタープライズ VoIP.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822407"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する

Create or modify a Group Call Pickup number range in Skype for Business Server エンタープライズ VoIP.

グループ通話ピックアップはコール パーク アプリケーションに基づいて作成されます。 グループ通話ピックアップを展開する場合は、通話ピックアップ グループ番号として指定された電話番号の範囲でコール パーク オービット テーブルを構成する必要があります。 これらのグループ番号は、別のユーザーに呼び出し音を鳴らしている通話を受け取るユーザーがダイヤルする番号です。

コール パーク オービット番号と同様に、通話ピックアップ グループ番号は、ユーザーまたは電話が割り当てられていない仮想内線番号である必要があります。 グループ通話ピックアップを展開する各フロントエンド プールには、1 つ以上の通話ピックアップ グループ番号の範囲を設定できます。 グループ番号の範囲は、展開内でグローバルに一意である必要があります **。GroupPickup の種類として割り当てる必要** があります。

コール パーク オービット テーブル内の通話ピックアップ グループ番号範囲を作成または変更するには、次の手順を使用します。

> [!NOTE]
> Skype for Business Server 管理シェルを使用して、コール パーク オービット テーブル内のグループ通話ピックアップ番号範囲を作成、変更、削除、および表示する必要があります。 グループ通話ピックアップ番号の範囲は、Skype for Business Server コントロール パネルでは使用できません。

通話ピックアップ グループ番号の範囲は、次のルールに準拠している必要があります。

- 範囲の開始番号が終了番号より大きくならないようにしてください。

- 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

- 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

- 番号範囲が文字または #で始まる場合、範囲は \* 100 より大きい必要があります。

- 有効な値: 正規表現文字列 ([ \\ *|#]?[1-9]\d {0,7} )|([1-9]\d {0,8} )。 つまり、値は、文字または # で始まる文字列、または 1 ~ 9 の数字 (最初の文字は \* 0 にすることはできません) である必要があります。 最初の文字が #または #の場合、次の文字は 1 ~ \* 9 の数値である必要があります (ゼロにすることはできません)。 後続の文字には、0 ~ 9 の任意の数字を指定できます (たとえば \* 、"#6000"、"92000"、"95551212"、"915551212")。 \* 最初の文字がそれ以外または #の場合、最初の文字は 1 ~ 9 の数値 (ゼロにすることはできません)、0 ~ 9 の最大 8 文字を指定する必要があります \* (たとえば、"915551212"、"41212"、"300")。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップ グループの範囲を作成または変更するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**

2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

3. **New-CsCallParkOrbit** を使用して、通話ピックアップ グループ番号の新しい範囲を作成します。 **Set-CsCallParkOrbit** を使用して、通話ピックアップ番号の既存の範囲を変更します。

    コマンド ラインで、次のコマンドを実行します。

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    次に例を示します。

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    次の例は、コール パーク オービットから通話ピックアップ グループに番号の範囲を変更する方法を示しています。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > このコマンドレットを使用して番号範囲に割り当てられた種類を変更できるのは、最初に正しくない種類を指定したが、グループ範囲がまだ使用されていない場合のみです。 番号範囲を CallPark から GroupPickup に変更した場合、またはその逆に番号範囲が既に使用されている場合は、コール パークまたはグループ通話ピックアップのどちらかが、その番号範囲で機能しなくなります。 たとえば、番号範囲を CallPark から GroupPick に変更すると、コール パーク アプリケーションは、その範囲のオービットを使用して通話をパークできなくなりました。

## <a name="see-also"></a>関連項目

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コール パーク オービット範囲の削除](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
