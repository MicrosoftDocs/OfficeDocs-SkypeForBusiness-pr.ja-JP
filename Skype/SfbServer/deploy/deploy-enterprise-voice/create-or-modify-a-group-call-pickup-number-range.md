---
title: 作成またはビジネス用の Skype のコール ピックアップのグループ番号の範囲を変更します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype のコール ピックアップのグループ番号の範囲を変更します。
ms.openlocfilehash: d73b3e72aa7cd5f733406c861d8a3357fe28fe45
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883954"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>作成またはビジネス用の Skype のコール ピックアップのグループ番号の範囲を変更します。

作成またはビジネス サーバーのエンタープライズ VoIP の Skype のコール ピックアップのグループ番号の範囲を変更します。

グループ コール ピックアップは、コール パーク アプリケーションに基づいています。 コール ピックアップのグループを配置するときは、コール ピックアップ グループの番号として指定されている電話番号の範囲のコール パークの移動テーブルを構成しなければなりません。 ユーザーはこのグループ番号にダイヤルし、他のユーザーに着信している通話をピックアップします。

コール パーク オービットの番号と同様に、通話ピックアップのグループ番号には、ユーザーや電話が割り当てられていない仮想の内線番号を使用する必要があります。 コール ピックアップのグループを展開する各フロント エンド プールでは、コール ピックアップ グループ番号の 1 つまたは複数の範囲を持つことができます。 このグループ番号範囲は、展開全体でグローバルに一意である必要があり、**GroupPickup** の種類として割り当てることも必要です。

次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。

> [!NOTE]
> 作成、変更、削除、および呼び出し公園軌道テーブルのグループを呼び出すピックアップの数値の範囲を表示するビジネス サーバー管理シェルの Skype を使用してください。 グループ ピックアップの電話番号の範囲は、ビジネス サーバーのコントロール パネルの Skype でご利用いただけません。

通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。

- 範囲の開始番号が終了番号より大きくならないようにしてください。

- 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

- 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

- 番号の範囲が、文字で始まる場合\*#、範囲は 100 より大きい値である必要がありますか。

- 有効な値: 正規表現の文字列に一致する必要があります ([\\* | #] ? [1-9] \d{0,7})。(1 ~ 9 の \d{0,8})。 つまり、値は、いずれかの文字で始まる文字列である必要があります\*#、または数字 1 ~ 9 の (最初の文字はゼロであることはできません)。 最初の文字の場合\*#、次の文字は数字 1 ~ 9 の (0 にすることはできません) である必要がありますか。 以降の文字は、任意の数の 0 から 9 までの 7 つの追加文字を使用できます (たとえば、「#6000」、「\*92000"、"\*95551212"、および"915551212"). 最初の文字がない場合\*#、最初の文字は、最大 8 個までの文字の後に数字 1 ~ 9 (0 にすることはできません) である必要がありますまたは各数値 0 から 9 (たとえば、「915551212」、「41212」、「300」)。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップ グループの範囲を作成するには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. コール ピックアップ グループ番号の新しい範囲を作成するのにには、**新しい CsCallParkOrbit**を使用します。 **セット CsCallParkOrbit**を使用すると、コール ピックアップ番号の既存の範囲を変更できます。

    コマンド ラインで、次のコマンドを実行します。

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例:

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。 番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。 たとえば、番号の範囲を CallPark から GroupPick に変更する場合は、コール パーク アプリケーションことができます公園の呼び出しに軌道の範囲は使用できません。

## <a name="see-also"></a>関連項目

[新しい-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[セット CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コール パークの移動範囲を削除します。](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)