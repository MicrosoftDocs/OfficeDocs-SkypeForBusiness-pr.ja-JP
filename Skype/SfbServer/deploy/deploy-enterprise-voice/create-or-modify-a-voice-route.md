---
title: Skype for Business でボイス ルートを作成または変更する
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '概要: Skype for Business Server コントロール パネルを使用して、Skype for Business Server でボイス ルートを作成または変更する方法について学習します。'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820457"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Skype for Business でボイス ルートを作成または変更する
 
**概要:** Skype for Business Server コントロール パネルを使用して、Skype for Business Server でボイス ルートを作成または変更する方法について学習します。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してボイス ルートを作成するには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、****または****CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**ルート**] をクリックします。
    
5. [ **新規] を** クリックして [新 **しいボイス ルート] ダイアログ** ボックスを表示します。
    
6. [ **名前]** に、音声ルートのわかりやすい名前を入力します。
    
7. (省略可能)[ **説明] に**、音声ルートに関するその他の説明情報を入力します。
    
8. このルートに対応するパターンを指定するには、[パターンの作成] ツールを使用して正規表現を生成するか、正規表現を手動で記述します。
    
   - **一致パターン構築** ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。
    
   - **許可する番号の開始番号**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。 たとえば、「+425」と入力し、[追加] を **クリックします**。 このルートに含める各プレフィックス値について、この手順を繰り返します。
    
   - **例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、**[例外]** をクリックします。 このルートに対応しない一致パターンの 1 つ以上の値を入力します。 たとえば、+425237 で始まる番号をルートから除外するには、[例外] フィールドに値 +425237 を入力し **、[OK]** をクリックします。 
    
   - 一致パターンを手動で定義するには、**一致パターン構築** ツールの **[編集]** をクリックし、.NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。 正規表現を記述する方法の詳細については [、「".NET Framework Regular Expressions"」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
9. 通話を発信する電話の ID を呼び出し先に表示しない場合は、**[発信者 ID を表示しない]** を選択します。 このオプションを選択する場合は、受信者の発信者 **番号** の表示に表示される代替発信者番号を指定する必要があります。
    
10. 1 つ以上のトランクをボイス ルートに関連付ける場合は、[追加] **をクリックし** 、一覧からトランクを選択します。
    
11. 1 つ以上の公衆交換電話網 (PSTN) 使用法をボイス ルートに関連付ける場合は、[選択] をクリックして、エンタープライズ VoIP 展開用に定義されている PSTN 使用法レコードの一覧からレコードを選択します。
    
    > [!NOTE]
    > 使用可能な各 PSTN 使用法レコードのプロパティを表示するには、「Skype for Business での PSTN 使用法 [レコードの表示」を参照してください](view-pstn-usage-records.md)。 > PSTN 使用法レコードを作成または編集するには[、「Create or modify a voice policy and configure PSTN usage records in Skype for Business」を参照してください](voice-policy-and-pstn-usage-records.md)。
  
12. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 リスト内でのレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。
    
    > [!NOTE]
    > PSTN 使用法レコードの一覧の順序が重要である音声ポリシーとは対照的に、PSTN 使用法レコードがボイス ルートに表示される順序は重要ではありません。 ただし、使用頻度で一覧を整理することをお勧めします。 例: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。 (Skype for Business Server は一覧を上から下にスキャンします)。 
  
13. (オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。
    
14. **[OK] を** クリックしてボイス ルートを保存します。
    
    > [!IMPORTANT]
    > ボイス ルートを作成するたびに、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については [、「Publish pending changes to the voice routing configuration in Skype for Business 」を参照してください](voice-route-config-changes.md)。 
  
### <a name="to-modify-a-voice-route"></a>ボイス ルートを変更するには

1. Skype for Business Server コントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**音声ルート**] をクリックし、[**ルート**] をクリックします。
    
3. **[ルート]** ページで、次のいずれかの方法を使用してボイス ルートを変更します。
    
   - ボイス ルート名をクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。
    
   - ボイス ルート名をクリックし、**[編集]** をクリックし、**[コピー]** をクリックしてから、**[貼り付け]** をクリックします。 直前に作成したボイス ルートの新しいコピーをクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。
    
4. **[ボイス ルートの編集]** ページの **[名前]** フィールドに、ボイス ルートのわかりやすい名前を入力します。
    
5. (オプション) **[説明]** フィールドに、ボイス ルートのわかりやすい追加情報を入力します。
    
6. このルートが対応するパターンを指定するには、**一致パターン構築** ツールを使用して正規表現を生成するか、手動で正規表現を記述します。
    
   - **一致パターン構築** ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。
    
   - **許可する番号の開始番号**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。 たとえば、「+425」と入力して、**[追加]** をクリックします。 このルートに含める各プレフィックス値について、この手順を繰り返します。
    
   - **例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、**[例外]** をクリックします。 このルートに対応しない一致パターンの 1 つ以上の値を入力します。 たとえば、+425237 で始まる番号をルートから除外するには、[例外] フィールドに値 +425237 を入力し **、[OK]** をクリックします。 
    
   - 一致パターンを手動で定義するには、[一致するパターンの作成] ツールで [編集] をクリックし、.NET Framework 正規表現を入力して、ルートが適用される宛先電話番号の照合パターンを指定します。正規表現を記述する方法の詳細については[、「".NET Framework Regular Expressions"」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
7. 発信 **呼び出しを** 行っている電話の ID を呼び出し先に表示しない場合は、[発信者番号を表示しない] を選択します。 このオプションを選択する場合は、受信者の発信者 **番号** の表示に表示される代替発信者番号を指定する必要があります。
    
8. 1 つ以上の公衆交換電話網 (PSTN) トランクをボイス ルートに関連付ける場合は、[追加] をクリックし、一覧からトランクを選択します。
    
9. 1 つ以上の PSTN 使用法をボイス ルートに関連付ける場合は、[選択] をクリックして、展開用に定義されている PSTN 使用法レコードの一覧からレコードエンタープライズ VoIPします。
    
    > [!NOTE]
    > 使用可能な各 PSTN 使用法レコードのプロパティを表示するには、「Skype for Business での PSTN 使用法 [レコードの表示」を参照してください](view-pstn-usage-records.md)。 > PSTN 使用法レコードを作成または編集するには、「Create [or modify a voice policy and configure PSTN usage records in Skype for Business」を参照してください](voice-policy-and-pstn-usage-records.md)。 
  
10. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 リスト内でのレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。
    
    > [!NOTE]
    > PSTN 使用法レコードの一覧の順序が重要な音声ポリシーとは対照的に、ボイス ルートでの PSTN 使用法レコードの順序は重要ではありません。 ただし、使用頻度で一覧を整理することをお勧めします。例: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。 (Skype for Business Server は一覧を上から下にスキャンします)。 
  
11. (オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。
    
12. **[OK]** をクリックします。
    
13. **[ルート]** ページの **[確定]** をクリックして、**[すべて確定]** をクリックします。 
    
    > [!NOTE]
    > ボイス ルートを作成または変更するたびに、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business での PSTN 使用法レコードの表示](view-pstn-usage-records.md)
  
[音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)
  
[Skype for Business での音声ルーティング構成に対する保留中の変更の公開](voice-route-config-changes.md)

