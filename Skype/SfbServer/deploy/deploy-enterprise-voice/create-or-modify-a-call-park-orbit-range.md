---
title: 作成またはビジネス用の Skype でコール パークの移動範囲を変更します。
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype では、コール パーク軌道範囲テーブルを変更します。
ms.openlocfilehash: 6892c48c95b7c5e84242a1456855e869a70e532b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370692"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>作成またはビジネス用の Skype でコール パークの移動範囲を変更します。

作成またはビジネス サーバーのエンタープライズ VoIP の Skype では、コール パーク軌道範囲テーブルを変更します。

パークでは、呼び出しを駐車場の軌道を使用します。 ユーザーは駐車し、呼び出しを取得する前に、コール パーク軌道テーブルを構成する必要があります。 パーク プール処理のそれぞれの範囲を指定することで内線番号 (軌道) を組織は呼び出しを駐車場の予約し、これらの範囲のルーティングを定義の範囲を指定する必要があります。 軌道の範囲を定義するときでは、1 つの軌道がいないため、多くの軌道が拡張機能をユーザーが使用できるその他のサービスの数を制限することが早すぎる、再利用しないように十分な軌道にします。 コール パーク アプリケーションが展開されているビジネス サーバー プールの各 Skype の複数のコール パークの移動範囲を作成します。 各コール パークの移動範囲には、グローバルに一意の名前と拡張子の一意のセットが必要です。

> [!IMPORTANT]
> 一般的にオービット範囲には 100 未満のオービットが含まれます。1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。

オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。

> [!NOTE]
> コール パークの回り込みの数値と直接向きダイヤル (DID) 番号を割り当てることの移動テーブルはサポートされません。

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>作成または呼び出しを駐車場の番号の範囲を変更するビジネス サーバーのコントロール パネルの Skype を使用するには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。 詳細については、**セットアップのアクセス許可の委任**を参照してください。

2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。

4. [**コール パーク**] ページで、次のいずれかを実行します。

   - 新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。

     > [!NOTE]
     > オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。

   - 既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5. 最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。 あります。

   - 範囲の開始番号が終了番号より大きくならないようにしてください。

   - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

   - オービット範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

   - 軌道の範囲の文字で始まる場合\*#、範囲は 100 より大きい値である必要がありますか。

   - 有効な値: 正規表現の文字列に一致する必要があります ([\\* | #] ? [1-9] \d{0,7})。(1 ~ 9 の \d{0,8})。 つまり、値は、いずれかの文字で始まる文字列である必要があります\*#、または数字 1 ~ 9 の (最初の文字はゼロであることはできません)。 最初の文字の場合\*#、次の文字は数字 1 ~ 9 の (0 にすることはできません) である必要がありますか。 以降の文字は、任意の数の 0 から 9 までの 7 つの追加文字を使用できます (たとえば、「#6000」、「\*92000"、"\*95551212"、および"915551212"). 最初の文字がない場合\*#、最初の文字は、最大 8 個までの文字の後に数字 1 ~ 9 (0 にすることはできません) である必要がありますまたは各数値 0 から 9 (たとえば、「915551212」、「41212」、「300」)。

   - プール当たりの合計が 50,000 オービットを超えないようにしてください。各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。

6. **移行先サーバーの FQDN**、完全修飾ドメイン名 (FQDN) をクリックするか、コール パーク アプリケーションをホストするアプリケーション サービスの ID をサービスします。 オービット範囲の開始番号と終了番号で指定された範囲内の番号にパークされる通話は、すべてこのサーバーまたはプールにルーティングされます。

7. [**確定**] をクリックします。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>作成または呼び出しを駐車場の番号の範囲を変更する Skype ビジネス サーバー管理シェルを使用するには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. 軌道番号の新しい範囲を作成するのにには、**新しい CsCallParkOrbit**を使用します。 **セット CsCallParkOrbit**を使用すると、回り込み番号の既存の範囲を変更できます。

    コマンド ラインで、次のコマンドを実行します。

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例:

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>関連項目

[新しい-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[セット CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コール パークの移動範囲を削除します。](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)