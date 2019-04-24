---
title: クラウドの自動応答をセットアップする
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 設定し、組織の処理効率の呼び出しに自動応答をクラウドをテストする方法について説明します。
ms.openlocfilehash: 8ab3dd318e8ae4c815a78dcc8f7430b2b6d08b04
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218837"
---
# <a name="set-up-a-cloud-auto-attendant"></a>クラウドの自動応答をセットアップする

自動応答は、組織へのコールし、右の部門にそれらを取得するには、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを使用できます。 マイクロソフトのチーム管理センターを使用して、組織の自動応答を作成できます。 **音声**には、左側のナビゲーションで、**自動応答**を選択し、新しい自動アテンダントを作成する > **新規追加**します。

自動応答の詳細についてはする場合を参照してください[雲の自動応答は何ですか?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。



## <a name="step-1---get-started"></a>手順 1 - 開始します。

- 自動応答は、関連付けられているリソース アカウントを持っている必要があります。 リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。

> [!NOTE] 
> マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。

> [!CAUTION]
> 取得し、フリー ダイヤル電話番号を使用して、通信のクレジットを設定する必要があります。 この参照を行うに[通信のクレジットは何ですか?](what-are-communications-credits.md)し、[組織の通信のクレジットを設定](set-up-communications-credits-for-your-organization.md)。

> [!TIP]
> 演算子または**電話システム**のライセンスを持つオンラインのユーザーは、メニュー ・ オプションへの呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするか、Office 365 のプランを呼び出すことを割り当てることにする必要があります。 [ビジネス ライセンスの割り当ての Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。 Windows PowerShell を使用することもできます。 などを実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>ステップ 2 - 新しい自動応答の作成

> [!IMPORTANT]
> すべての自動応答は、関連付けられている[リソースのアカウント](manage-resource-accounts.md)を持っている必要があります。 最初に、リソース アカウントを作成する必要がありますし、自動応答に関連付けることができます。

### <a name="using-the-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターを使用してください。

**マイクロソフトのチーム管理センター**の [**音声**] をクリックします > **自動応答**、 **+ 新規**] をクリックします。

#### <a name="general-info-page"></a>[全般情報] ページ

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![ナンバー 1](media/sfbcallout1.png)

**名**自動アテンダントのわかりやすい表示名を入力します。 名前の入力は必須で、空白を含む最大 64 文字を含めることができます。 この名前は [ **自動応答**] タブの [ **名前**] 列に表示されます。

* * *

![ナンバー 2](media/sfbcallout2.png)

**リソース アカウント**新しい自動応答に接続する 1 つまたは複数のリソース アカウントを選択するのには、このボタンをクリックします。 すべての自動応答は、関連付けられているリソース アカウントを持っている必要があります。 リソース アカウントは、アカウントに関連付けられている電話番号を持つことができますが、その可能性があります。 通常、トップレベルの自動応答は、割り当てられた電話番号にリソース アカウントを持っていますが、(最初のレベルの自動応答に接続するレベル 2 のメニューとして使用) の入れ子になった自動応答には、リソース アカウントに割り当てられている電話番号を持たない可能性があります。

* * *

![ナンバー 3](media/sfbcallout3.png)

**タイム ゾーン** 自動応答にはタイム ゾーンを設定する必要があります。ただし、組織のメイン アドレスのタイム ゾーンと一致している必要はありません。各自動応答には、異なるタイム ゾーンを設定できます。自動応答の営業時間の設定は、ここで選択したタイムゾーンに基づきます。

* * *

![ナンバー 4](media/sfbcallout4.png)

**言語** 自動応答に使用する言語を、一覧表示されている使用可能な言語の中から選択します。 ここで設定した言語は、この自動の応答へのコールの人と対話する自動応答を使用し、この言語ですべてのシステム プロンプトが再生する言語です。

* * *

![ナンバー 5](media/sfbcallout5.png)

**オペレーター** このオプションは省略可能で、自動応答で設定する必要はありません。 ただし、電話することを支援してくれる人に話をするメニューを解除することをする人の**オペレーター**のオプションを設定できます。

オペレーターには、キー 0 が自動的に割り当てられます。

このセットアップをした場合、発信者に、[**営業時間の通話ハンドリング**] ページの [**メニュー オプションの編集**] で利用可能なオプションであることを伝える必要もあります。 自動応答でオペレーターを設定する場合は、 [**発信者が聞く内容**] ボックスに、対応するプロンプト テキストを入力するか、オーディオ ファイルを変更して、このオプションを含める必要があります。 たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。

次の項目のいずれかをオペレーターとして設定できます。

- Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。

     > [!Note]
     > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。

- **キューの呼び出し**を設定しました。
- 発信者がボイスメールに送られるように設定できます。 これを行うには、**あなたの会社の担当者**を選択し、ボイスメールに直接転送するのにはこのメンバーの呼び出しを設定します。

* * *

![ナンバー 6](media/sfbcallout6.png)

**音声入力を有効にします。** 音声認識機能では、このオプションが選択されている場合があります。 人を呼び出すには、[設定した言語](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)で音声入力を使用できます。 のみ、電話のキーパッドを使用してユーザーを許可する場合にオフに設定し、音声認識機能を無効にできます。

* * *

選択が終わったら [**次へ**をクリックします。

#### <a name="business-hours-page"></a>営業時間ページ

既定では、営業時間は午後 5 時まで、月曜日から金曜日までの 9 am に設定されます。  営業時間に含まれない時間は営業時間外として考慮されます。 **24/7 を選択**をするとすべての時間の業務時間をクリックすることができます。 **24/7 を選択する**オプションを選択した場合を除き、業務時間終了後、自動アテンダントの処理の呼び出しを構成するのには**時間の設定の呼び出し後**のページが使用されます。

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![ナンバー 1](media/sfbcallout1.png)

既定では、営業時間は月曜日から金曜日、午前 9時 00分 ~ 午後 5時 00分に設定されます。 スケジュール内のすべての時間時間の選択を解除するオプションを**オフにすべての時間**を選択します。 **既定値にリセット**を選択すると、営業時間は月曜日から金曜日、午前 9時 00分 ~ 午後 5時 00分にリセットされます。

* * *

![ナンバー 2](media/sfbcallout2.png)

営業時間を変更するには、予定表を使用して設定したい営業時間を選択してください。 予定表を使用すると、30 分間隔で営業時間を選択できます。ここで選択する営業時間は、[**全般情報**] ページで設定したタイム ゾーンに基づいて設定されます。 休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。 営業時間内に複数の休憩時間を設定できます。

* * *

選択が終わったら [**次へ**をクリックします。

#### <a name="business-hours-call-settings"></a>営業時間の設定を呼び出す

> [!TIP]
> カスタムの勤務時間のスケジュールを使用する場合**営業時間の設定の呼び出し**と同様のオプションを与える**時間の問い合わせ対応後**ページを使用して、業務時間終了後の処理の呼び出しを設定する必要がありますがもします。

その人が勤務時間中に、組織の自動応答の電話番号への呼び出しが聞こえますごきげんよう、プロンプト、およびメニューを設定できます。

![営業時間は、処理を呼び出します。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![営業時間内の呼び出しの処理を継続します。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![ナンバー 1](media/sfbcallout1.png)

**あいさつ文の挿入**業務時間の案内応答は省略可能で**ない応答メッセージ**に設定することができます。 この例では、呼び出し元が鳴らないメッセージまたは応答メッセージで選択したアクションのいずれかの呼び出しを処理する前に。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。

- **なしのあいさつ文**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。
- **オーディオ ファイルをアップロード**これを選択する場合は、あいさつ文を記録し、オーディオ (.wav、.mp3 や .wma 形式) でファイルをアップロードしています。
- **あいさつのメッセージの種類**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。 たとえば、「Contoso へようこそ。 お電話ありがとうございます。 などと、[**発信者が聞く内容**] ボックスに入力できます。

* * *

![ナンバー 2](media/sfbcallout2.png)

営業時間中に着信する呼び出しに対する動作内容を選択できます。 次のアクションから選択できます。

- **切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。
- **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
  - エンタープライズ VoIP を有効にするか Office 365 のプランを呼び出すことを割り当てられている**電話システム**のライセンスは、**会社の担当者**です。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。

    > [!Note]
    > **会社の担当者**は、オンラインのユーザーまたはユーザーには、設置がホストされているビジネス サーバー 2015 または Lync Server 2013 の Skype を使用します。

   - 別**の自動応答**

   既存の自動応答を使用すると、サブメニューを含むメニューのオプションの 2 番目のレベルを作成します。 これらは入れ子の自動応答と呼ばれます。 入れ子になった自動応答に呼び出しを送信するには、**会社の担当者**を選択し、いずれかの関連付けられた自動応答またはしたら、自動応答と関連するすべてのものが既にある、リソース アカウントを割り当てるこの自動応答を作成します。

- **再生] メニュー オプション**は、再生するプロンプトを設定することにも使用できます。

* * *

![ナンバー 3](media/sfbcallout3.png)

**メニュー プロンプト**メイン メニューのプロンプトを作成するには、音声合成を使用するか、オーディオ ファイル (.wav、.mp3 や .wma ファイル) をアップロードします。 **呼び出し元に、メニューのナビゲーションの設定**] ボックスに、プロンプトを入力するか、記録、オーディオ ファイルと、たとえば:"販売と言いますか、または 1 を言います。 サービスは、キーを押してまたは 2 を言います。 カスタマー サポートでは、キーを押してまたは 3 と答えるとします。 演算子を押すか、0 と答えてください。 このメニューをもう一度聞くには、アスタリスク キーを押しますの繰り返しを言う」 **あいさつのメッセージの種類**これを選択した場合 (1000 文字以内) を読み取るシステムを設定するテキストを入力する必要があります。 **オーディオ ファイルをアップロード**これを選択した場合は、応答メッセージを記録し、オーディオ ファイル (.wav、mp3 または .wma 形式) をアップロードし、必要があります。

* * *

![ナンバー 4](media/sfbcallout4.png)

**メニューの [オプション]** キーパッドのキーのボタンを使用してメニュー オプションを追加または削除できます。 メニュー オプションを追加するを押して**ダイヤル キーを割り当てます**。 下のオプションの対応する行が表示されます。 メニュー オプションを削除するには、キーパッド制御に対応するキーの左側にクリックし、上の [削除] アイコンをクリックします。 キー マッピング行が削除されます。

> [!TIP]
> メニュー プロンプトのテキストを更新または再録音とは別に既存のメニューのプロンプトを自動的に行われませんので、オプションを削除するのに追加する場合する必要があります。  
>
>メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。 たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。

> [!NOTE]
> キー \* (繰り返し) と\#(戻る)、システムによって予約されており、再割り当てすることはできません。 音声認識が有効になっている場合、* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。

ダイヤル キーを選択した後に、メニューのオプションを設定する必要があります。

- オプションの**音声コマンド**を入力します。 最大 64 文字を入力でき、これと、「顧客サービス」または「操作土地とします」のように複数の単語を含めることができます。 音声認識を有効にしている場合は、名前は自動的に認識されます。発信者は 3 を押すか、「さん」と音声入力するか、または 「顧客サービス」 と音声入力して、キー 3 にマッピングされたオプションを選択することができます。
- 呼び出しのかどうか、対応するキーが押された、またはオプションを選択する音声認識機能を使用して送信する先を選択します。 次の場所に呼び出しを送信できます。

  - **オペレーター** オペレーターがすでにセットアップされている場合は、キー 0 に自動的にマッピングされますが、削除するか別のキーに割り当てることもできます。 オペレーターがどのキーにも設定されていない場合は、音声コマンド 「オペレーター」 も無効になります。
  - Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者** 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**社内の担当者**を選択しの呼び出しは、ボイスメールに直接転送するには、このユーザーを設定します。

    > [!Note]
    > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 
    - 別**の自動応答**

       既存の自動応答を使用すると、サブメニューを含むメニューのオプションの 2 番目のレベルを作成します。 これらは入れ子の自動応答と呼ばれます。 入れ子になった自動応答に呼び出しを送信するには、**会社の担当者**を選択し、いずれかの関連付けられた自動応答またはしたら、自動応答と関連するすべてのものが既にある、リソース アカウントを割り当てるこの自動応答を作成します。

        > [!Note]
        > 入れ子 (または第 2 レベル) の自動応答の **営業時間** も使用されます。これには、セットアップされた他の自動応答から送信された呼び出しへ向けたものも含まれます。

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![ナンバー 5](media/sfbcallout5.png)

**名前によるダイヤル** このオプションを選択すると、発信者はディレクトリ検索を使用して組織内の人を検索することができます。 [**ダイヤル スコープ**] ページでこれらのオプションをセットアップすることにより、名前によるダイヤルで誰が対応可能または対応不可として一覧表示されるのかを選択することができます。 **電話システム** のライセンスをもつオンライン ユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされているユーザーであれば、名前によるダイヤルで探すことができます。


* * *

選択が終わったら [**次へ**をクリックします。

#### <a name="holiday-call-settings"></a>休日呼び出しの設定

各自動応答には、最大 20 個の決められた休業日を追加できます。

> [!TIP]
> 移動することができます、**組織全体の設定**時に画面 > の呼び出しハンドラーを新規作成の一部として、**祝日**を休日、またはを作成するを作成できます。

![自動応答で休業日をセットアップする](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![ナンバー 1](media/sfbcallout1.png)

その他の自動応答を既に作成した場合は、オプションを使用するか、このリストに必要な情報を編集するを参照してください可能性があります。 それ以外の場合は、新しい呼び出しハンドラーを作成する必要があります。

新しい呼び出しハンドラーを追加するには、**ハンドラーを呼び出して新規 +** をクリックします。

* * *

![自動アテンダントの続きで休日を設定](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![ナンバー 1](media/sfbcallout1.png)

新しいウィンドウで、画面の上部にある新しい呼び出しハンドラーの名前を入力します。

![ナンバー 2](media/sfbcallout2.png)

**休日**のプルダウン ・ リストで既に、休日の名前が存在する場合を使用することができます。 休日の名前をする必要がありますが既に存在しない場合は、プルダウン ・ リストおよび割り当ての名前と新しい画面が表示されたら新しい休日の日付で**新しい祝日を作成する**を選択します。 準備ができたら、**保存**をクリックします。

休業日名は最大 64 文字で構成でき、同じ自動応答に対して一意である必要があります。 たとえば、同じ自動応答で 「感謝祭」という名前の休業日を 2 つもつことはできません。

![ナンバー 3](media/sfbcallout3.png)

**あいさつ文の挿入**あいさつ文は省略可能で**ない応答メッセージ**に設定することができます。 この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。

- **なしのあいさつ文**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。
- **オーディオ ファイルをアップロード**これを選択する場合は、時候のあいさつを記録し、オーディオ ファイル (.wav、.mp3 や .wma 形式) をアップロードし、
- **あいさつのメッセージの種類**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。 たとえば、「あけましておめでとうございます。 当社は現在、休業中です。」 **あいさつのメッセージの種類**] ボックスにします。

![ナンバー 4](media/sfbcallout4.png)

**アクション**このホリデー シーズン中に着信した呼び出しの動作を選択します。 次のオプションから選択できます。

- **切断** 休業日の応答メッセージが流れてから、通話が切断されます。
- **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
  - Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**あなたの会社の人**を選択し、この人を通話をボイスメールに直接転送します。

    > [!Note]
    > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 

  - **キューの呼び出し**を設定している既存の呼び出し待ち行列への呼び出しを転送します。
  - 別**の自動応答**、2 番目のレベルのサブメニューを含むメニュー オプションを作成します。 これらは入れ子の自動応答と呼ばれます。

    > [!Note]
    > 既定では、休業期間中に着信したすべての呼び出しは、応答メッセージの後に切断されます。よって、違うビヘイビアーが望ましい場合には、リダイレクトを指定する必要があります。

#### <a name="select-dial-scope-page"></a>ダイヤルの範囲を選択ページ

このページには、組織内のどのユーザーになりますディレクトリに一覧表示されているとダイヤルの利用可能な場合で組織を呼び出す人の名前でを設定することができます。

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![1](media/sfbcallout1.png)を**含める**] オプションを使用すると、2 つのオプションがあります。

- **すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。 **電話システム** のライセンスをもつすべての Online ユーザーと、Office 365 の通話プランをもつ、Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーが一覧表示されます。
- **カスタム ユーザー グループ**このオプションを使用して、Office 365 のグループ、配布リスト、または組織内で作成されたセキュリティ グループを検索することができます、人がこの Office 365 のグループ、配布リスト、またはいずれかの**は、ユーザー セキュリティ グループにでオンラインのユーザーを追加する場合、電話システムのライセンス**またはオンプレミスでホストされているビジネス サーバー 2015 または Lync Server 2013 の Skype を使用しています。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。

* * *

![ナンバー 2](media/sfbcallout2.png)

**除外**オプションを使用すると、2 つのオプションがあります。

- **なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外しません。
- **カスタム ユーザー グループ**このオプションを使用する場合、Office 365 のグループ、配布リスト、または組織内で作成されたセキュリティ グループを検索することができますおよびすべてのユーザーが Office 365、そのグループに配布リストを追加またはセキュリティ グループは、ディレクトリ検索から除外されます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。

> [!NOTE]
> ディレクトリに一覧表示、ダイヤルを使用するときに名前で音声認識でその名前を持つ新しいユーザーには、最大で 36 時間がかかる場合があります。

すべての必須フィールドに入力して、メニューとオプションを処理する呼び出しを設定して後、は、[**送信**] をクリックします。

## <a name="editing-and-testing-auto-attendants"></a>編集と自動応答をテストします。

自動応答を保存すると、[ **自動応答**] ページに表示されます。 これによって、迅速にいくつかのオプションを設定するなどの名前、電話番号、言語、およびステータスを参照してください。

自動応答を変更する場合は、自動応答を選択し、操作ウィンドウの [**編集**] をクリックします。

アクション ペインで、[**テスト**] ボタンを使用して、自動アテンダントをテストの呼び出しも簡単に配置できます。

## <a name="want-to-know-more"></a>詳細情報

Windows PowerShell を使用して自動応答を作成し、設定することもできます。

### <a name="auto-attendant-cmdlets"></a>自動応答のコマンドレット

自動応答で管理する必要があるコマンドレットを以下に示します。

- [新しい-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [セット CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [Get CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [Get CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [削除 CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [新しい-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [新しい-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [新しい-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [エクスポート CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [Get CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新しい-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [インポート-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [新しい-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell では、Office 365 と一元管理を行う複数のタスクがある場合、日常的な作業を簡素化するを使用してマイクロソフトのチームを管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Office 365 の PowerShell では、Office 365 を管理します。](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連トピック

[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[サービス電話番号を取得する](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)

[小規模ビジネスの例: 自動応答をセットアップする](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
