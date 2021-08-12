---
title: グループ通話ピックアップの番号範囲を作成または変更Skype for Business
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
description: グループ通話ピックアップの番号範囲を作成または変更Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 73c2c0b74c27fd59d94d97c5ee05e0da88219601e839d42dc12e0ec659db0aa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307878"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>グループ通話ピックアップの番号範囲を作成または変更Skype for Business

グループ通話ピックアップの番号範囲を作成または変更Skype for Business Server エンタープライズ VoIP。

グループ通話ピックアップは、コール パーク アプリケーションに基づいて行います。 グループ通話ピックアップを展開する場合は、通話ピックアップ グループ番号として指定された電話番号の範囲でコール パーク オービット テーブルを構成する必要があります。 これらのグループ番号は、ユーザーがダイヤルして別のユーザーの呼び出しを呼び出す番号です。

通話パークオービット番号と同様に、通話ピックアップ グループ番号は、ユーザーまたは電話が割り当てられていない仮想内線番号である必要があります。 グループ通話ピックアップを展開する各フロントエンド プールには、1 つ以上の範囲の通話ピックアップ グループ番号を使用できます。 グループ番号の範囲は展開でグローバルに一意である必要があります **。GroupPickup の種類として割り当てる必要** があります。

コール パーク オービット テーブルで通話ピックアップ グループ番号範囲を作成または変更するには、次の手順を使用します。

> [!NOTE]
> コール パーク オービット テーブルSkype for Business Serverグループ通話ピックアップ番号範囲を作成、変更、削除、および表示するには、グループ管理シェルを使用する必要があります。 グループ通話ピックアップ番号の範囲は、コントロール パネルSkype for Business Server使用できません。

通話ピックアップ グループ番号の範囲は、次のルールに準拠している必要があります。

- 範囲の開始番号が終了番号より大きくならないようにしてください。

- 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

- 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

- 数値範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。

- 有効な値: 正規表現文字列と一致する必要があります ([ \\ *|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8} つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。 最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。 後続の文字には、0 ~ 9 の任意の数字 \* ("#6000"、"92000"、"95551212"、"915551212" など) を \* 指定できます。 最初の文字がまたは #の場合、最初の文字は 1 から 9 の数字 (ゼロにすることはできません)、その後に最大 8 文字の数字 \* ("915551212"、"41212"、"300" など) が続きます。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップ グループ範囲を作成または変更するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「代理セットアップのアクセス許可」の説明に従って必要なユーザー権限でログオン **します。**

2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

3. **New-CsCallParkOrbit** を使用して、新しい範囲の通話ピックアップ グループ番号を作成します。 **Set-CsCallParkOrbit** を使用して、通話ピックアップ番号の既存の範囲を変更します。

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
    > このコマンドレットを使用して、番号範囲に割り当てられた種類を変更できるのは、最初に正しくない型を指定し、グループ範囲がまだ使用されていない場合のみです。 番号範囲を CallPark から GroupPickup または GroupPickup に変更し、その番号範囲が既に使用されている場合は、コール パークまたはグループ通話ピックアップのどちらかが、その番号範囲で動作を停止します。 たとえば、番号範囲を CallPark から GroupPick に変更した場合、コール パーク アプリケーションでは、その範囲のオービットを使用して呼び出しをパークできなくなりました。

## <a name="see-also"></a>関連項目

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コール パーク オービット範囲の削除](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)