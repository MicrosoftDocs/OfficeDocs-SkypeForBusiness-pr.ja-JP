---
title: Exchange ユニファイド メッセージングの移行サポート
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft は、2020 年 2 月 28 日までに、Exchange ユニファイド メッセージング オンライン (ExchUMO) サービスを廃止します。 この記事では、影響を受けるお客様がビジネス継続性を計画するために知っておくべきことと行うべきことをまとめたものです。
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676369"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange ユニファイド メッセージングの移行サポート

> [!IMPORTANT]
> **Exchange Onlineのユニファイド メッセージング サービスは、2020 年 2 月 28 日午後 5 時 (太平洋時) の時点でサポートされていません。すべてのボイスメール アカウントは、Microsoft によってクラウド ボイスメール サービスに移行されました。残りの自動応答トラフィックは監視されないため、いつでも中断される可能性があります。**

2019 年 2 月 8 日の[発表](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)に関連して、Microsoft は 2020 年 2 月 28 日までに Exchange ユニファイド メッセージング オンライン (ExchUMO) サービスを廃止します。 この記事では、影響を受けるお客様がビジネス継続性を計画するために知っておくべきことと行うべきことの概要について説明します。

ExchUMO は、ボイスメール、自動応答、通話キュー、FAX 統合サービスのために顧客によって展開されます。 Microsoft では、Skype for Business Online およびMicrosoft Teamsで既に数千のお客様をサポートしている電話システム サービスへの移行を支援する予定です。

ボイスメールは主に Microsoft 主導の移行です。管理者の関与や投資が顧客のサブセットに必要な場合があります。 自動応答は管理者主導の移行です。クラウド自動応答クラウド サービスで既存の ExchUMO 自動応答ツリーを再作成する必要があります。 サードパーティの PBX で ExchUMO 機能を使用している顧客は、サードパーティの PBX システムをサポートしていないため、Skype クラウド サービスに移行されません。 [このブログ](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)では、サード パーティサポートの廃止計画が発表されました。この展開モデルのお客様は、ユーザーを Microsoft のユニファイド コミュニケーション プラットフォーム/サービスのいずれかに移行したり、これらのユーザーに対してサードパーティのボイスメールや自動応答ソリューションを取得したりできます。 Fax の統合は、クラウドベースのサービスではサポートされていません。お客様はサード パーティのソリューションに移行する必要があります。

## <a name="who-is-affected"></a>影響を受けるWho

Exchange ユニファイド メッセージング オンライン サービスから次のいずれかの機能を使用しているお客様が影響を受ける。

- ボイスメール サービス
- 自動応答サービス
- キュー サービスの呼び出し
- FAX 統合

> [!Note]
> ユニファイド メッセージングでオンプレミスでExchange Serverを使用しているお客様は影響を受けられません。

ユーザー エクスペリエンスの影響におけるユーザーエクスペリエンスと管理者エクスペリエンスの [影響](#user-experience-impact)の詳細について説明します。

## <a name="migration-plan-overview"></a>移行計画の概要

Microsoft は、ExchUMO の機能を使用しているさまざまなお客様の展開を特定し、次の計画に基づいて顧客の移行を支援します。

|顧客グループ |タイムライン  |詳細  |
|---------|---------|---------|
|移行する準備ができているお客様<br><br>移行する機能:<br><ul><li>ボイスメール</ul>   |   2019 年 3 月 — 5 月  |例:<ul><li>    ボイスメールの簡単な展開と使用方法をお持ちのお客様<li>Microsoft が移行を実行するためのすべての要件が確立されているお客様<ul>|
|前提条件をお持ちのお客様<br><br>移行する機能:<br><ul><li>ボイスメール<li>自動応答<li>キューの呼び出し</ul> |  2019 年 5 月 - 12 月 |例: <br><ul><li>ハイブリッド構成が完了していない<li>ハイブリッド PSTN 番号が設定されていない</ul>|
|管理者の関与&顧客投資を必要とする顧客<br><br>移行する機能:<ul><li>voicemail<li>自動応答<li>通話キュー<li>FAX 統合</ul>| 2020 年 2 月までに  | 例: <br><ul><li>ExchUMO サービスはサード パーティの PBX によって使用されます<li>PSTN サブスクライバー アクセス要件をお持ちのお客様<li>SFB 2010 のお客様 (サポートされていません)<li>FAX 統合</ul> |

## <a name="voicemail-migration-guidelines"></a>ボイスメールの移行ガイドライン

### <a name="get-informed"></a>情報を取得する

[ブログのお知らせ](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)とこの記事を理解し、ユーザーのスムーズな移行を計画してください。 電話システムボイスメール機能の詳細については、「[ボイスメールとオプションSkype for Business確認](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)する」を参照してください。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Skype for Businessハイブリッド トポロジを確立する

Skype for Businessハイブリッド トポロジが確立されていない場合は、ボイスメール ユーザーのスムーズな移行を有効にする必要があります。 詳細については、「[ハイブリッドSkype for Business構成](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)する」を参照してください。

> [!Note]
> ボイスメール サービスの移行のためにユーザーをオンラインに移行する必要はありません。 ただし、オンプレミス ユーザーがボイスメール サービス電話システム利用するには、ハイブリッド トポロジを確立する必要があります。

### <a name="plan-your-auto-attendant-migration"></a>自動応答の移行を計画する

管理者はいつでも、自動応答を ExchUMO からクラウドの自動応答に移行できます。 詳細については、「 [クラウド自動応答を設定](/microsoftteams/create-a-phone-system-auto-attendant) する」を参照してください。

Microsoft は引き続き、お客様が移行に必要と考える可能性がある追加の自動応答機能を提供しています。 管理者は、機能セットを評価し、それに応じて自動応答インスタンスを移行する必要があります。 機能一覧の比較については、 [ExchUMO と Azure クラウドベースのサービスの機能マトリックス](#exchumo-and-azure-cloud-based-services-feature-matrix)を参照してください。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>ボイスメールの移行後の検証とテストを計画する

ボイスメールの移行は Microsoft 主導です。 前提条件のハイブリッド トポロジが確立されているため、管理者は何もする必要はありません。 Microsoft は、必要な検証とテストを実行して、ユーザーのボイスメールの移行が中断されないようにします。 管理者は、自分の側でテストと検証を実行することをお勧めします。 推奨 [されるテスト計画については、推奨されるテスト計画と管理者の移行後の検証](#suggested-test-plan-and-post-migration-validation-for-admins) に関する記事を参照してください。

> [!Note]
> Lync Server 2010 はサポートされていません。 2010 サーバーを展開している場合は、サーバーのアップグレードを計画するか、ユーザーをMicrosoft Teamsに移行することを検討する必要があります。  

### <a name="monitor-the-admin-notification-center"></a>管理通知センターを監視する

管理通知センターで、ユーザーの移行に関する詳細とタイムラインを確認してください。 通知は、移行期間の少なくとも 30 日前に送信されます。

> [!Note]
> ユーザーの移行タイムラインに関する通知を受け取り、ビジネス上重要な理由で移行を延期したい場合は、Microsoft サポートに問い合わせてください。 2020 年 2 月 28 日の廃止日を超えて移行を延期することはできません。 さらに質問がある場合は、アカウント チームまたはMicrosoft サポートにお問い合わせください。 Microsoft 365またはOffice 365を既に使用しているお客様は、Microsoft 365 管理センターを通じてサポート ケースを送信できます。

### <a name="consider-opting-in-for-a-planned-migration"></a>計画的な移行をオプトインすることを検討する

CVM へのボイスメール サービスの計画的な移行をオプトインできます。 オプトインする前に、この記事の詳細 (特に次のセクション) を確認してください。

- 移行手順 (このセクション)
- ExchUMO と Azure クラウドベースのサービス機能マトリックス
- ユーザー エクスペリエンスへの影響

マネージド移行を選択すると、Microsoft 365管理ポータル のメッセージ センターに移行前の 30 日間の通知は表示されません。

計画的な移行をオプトインするには、管理者のメール アドレスから次の情報を [cvm@microsoft.com](mailto:cvm@microsoft.com) に電子メール要求を送信します。

- 優先日 (火曜日): 移行ウェーブは毎週火曜日に実行されます。 2019 年 12 月 3 日を超えない火曜日の日付を選択してください。
 
- テナント ID: この形式の 32 文字の番号 0046728c-688a-4472-a38f-098fec60ac6x。 テナント ID は、Azure AD のMicrosoft 365管理ポータルまたは次の PowerShell コマンドレットを使用して確認できます。`Get-CsTenant | Select ObjectId`

テナントが正常に移行されると、電子メールで確認メッセージが表示されます。

## <a name="auto-attendant-migration-guidelines"></a>自動応答移行ガイドライン

Microsoft 365およびOffice 365組織の管理者は、2020 年 2 月 28 日の Exchange UMO サービス廃止日の前に、Microsoft Cloud Auto Attendant サービスで Exchange UM Online 自動応答を再作成し、オンプレミスの電話番号をそれらの電話番号に切り替える必要があります。 これは、新しいクラウド自動応答を正常に移行してテストするための推奨されるガイドラインです。 自動応答が多数ある場合は、[Exchange UM 自動応答からクラウド自動応答への移行スクリプトを](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)使用して、自動応答の一括移行を簡略化できます。

### <a name="auto-attendant-setup"></a>Auto attendantのセットアップ

直前の問題を回避し、Cloud Auto Attendant サービスの機能とエクスペリエンスを理解するために、新しい自動応答のセットアップを早期に開始することを強くお勧めします。 1 つ以上のギャップ機能を必要とする自動応答の場合は、ギャップ機能をデプロイの準備に使用できる場合に、自動応答を作成してテストできます。 ギャップ機能の詳細については、 [付録](#appendix)を参照してください。

1. [get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant) を使用して既存の自動応答の構成をエクスポートするには、Exchange UMO コマンドレットを使用します。  

2. Exchange Online PowerShell の [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) コマンドレットを使用して、グリーティング メディア ファイル (使用されている場合) をエクスポートし、.mp3形式に変換します。

3. [クラウド自動応答の計画とクラウド自動応答](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)の[設定](/microsoftteams/create-a-phone-system-auto-attendant)の手順に従って、Microsoft Teams管理センターまたは PowerShell を使用して自動応答を作成します。

4. メニュー オプションが変更された場合は、あいさつ文を確認します。

5. この記事の「 [既知の問題](#known-issues) 」セクションの「PSTN への自動応答通話転送」回避策を使用して、応答グループへの転送を構成します。  

6. 新しい自動応答を内部的に呼び出すか、テスト用の電話番号を割り当ててテストします。  

### <a name="cutover"></a>一括

1. 電話番号を UMO 自動応答Exchangeから新しい自動応答に切り替えます。
2. 連絡先オブジェクトからリソース アカウントに SIP URI を移動します。
3. 新しく割り当てられた電話番号を使用して、自動応答をテストして検証します。

## <a name="appendix"></a>付録

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO と Azure クラウドベースのサービス機能マトリックス

| サービス | 機能レベル | 機能 | 備考  | クラウド VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | サービスの機能| サード パーティ製 PBX をサポートする    | SIP 通知メッセージを使用して MWI (メッセージ待機インジケーター) などのサード パーティ製 PBX に提供されるすべての機能を含Exchange UM Online | N   | Y    |
| VM | サービスの機能  | サポート Skype for Business Server   |  | Y | Y    |
| VM | サービスの機能 | サポート Microsoft Teams|  | Y | N    |
| VM | サービスの機能 | 電子情報開示と保留  | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | サービスの機能 | Exchange 規則のサポート | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | ユーザーの機能 | PSTN ダイヤルイン アクセス  | サブスクライバー アクセス  | N | Y    |
| VM | ユーザーの機能 | 代理人  | 不在着信メール  | N | Y    |
| VM | ユーザーの機能 | PSTN Outlook Voice Access   | サブスクライバー アクセス  | N | Y    |
| VM | ユーザーの機能 | 認証されたエンドポイントを使用したダイヤルイン | ボイスメール サービスを呼び出して音声メッセージをリッスンし、ボイスメール設定を変更する| Y | Y    |
| VM | ユーザーの機能 | ボイスメールを無効にするユーザー設定   |  | Y | Y    |
| VM | ユーザーの機能 | 個人用あいさつ文を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザーの機能 | OOF あいさつ文を作成するためのユーザー設定  |  | Y | Y    |
| VM | ユーザーの機能 | 既定の言語を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザーの機能 | TTS で既定のあいさつ文を上書きするユーザー設定  |  | Y | N    |
| VM | ユーザーの機能 | 個人用あいさつ文を記録する (認証されたデバイス) |  | Y | Y    |
| VM | ユーザーの機能 | 個人のあいさつ文 (PSTN) を記録する — 電話で再生する |  | N | Y    |
| VM | ユーザーの機能 | 文字起こしを無効にするユーザー設定 |  | N | Y    |
| VM | ユーザーの機能 | 文字起こし  |  | Y | Y    |
| VM | ユーザーの機能 | SIP 通知メッセージを使用した MWI (メッセージ待機インジケーター) |  | N | Y    |
| VM | ユーザーの機能 | Outlookでの MP3 オーディオ ファイル形式    |  | Y | Y    |
| VM | ユーザーの機能 | 可変速度再生コントロール |  | Y | Y    |
| VM | ユーザーの機能 | ボイスメールを転送する  | 受信したボイスメールを他のユーザーに転送する | Y | Y    |
| VM | ユーザーの機能 | ユーザーのグループに音声メッセージを送信する  |ボイスメールブロードキャスト   | N | Y   |
| VM | ユーザーの機能 | 携帯ショートメールを使用したボイスメール通知    | ユーザーは、新しいボイスメールを持っているときに携帯ショートメールを受け取ることができます    | N | Y    |
| VM | ユーザーの機能 | サポートされているあいさつ文の言語 | ここでの詳細: [クラウド自動応答とは何ですか?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | ユーザーの機能 | 通話応答ルール |  | Y | Y    |
| VM | ユーザーの機能 | 電話で再生 (PSTN)- メッセージを再生する | 自分のセルに電話して音声メッセージを聞く  | N | Y    |
| VM | ユーザーの機能 | 電話で再生 (認証)- メッセージを再生する | 認証されたデバイスで電話をかける  | N | Y    |
| VM | ユーザーの機能 | 複数のユーザー間の共有メールボックス |  | Y | Y    |
| VM | 呼び出し元の機能  | 発信者エクスペリエンス — 保護されたボイスメール | 呼び出し元は、記録されたメッセージを保護済みとしてマークするオプションを選択できます| N | Y    |
| VM | 呼び出し元の機能  | 発信者エクスペリエンス — プライベート ボイスメール | 呼び出し元は、記録されたメッセージをプライベートとしてマークするオプションを選択できます  | N | Y    |
| VM | 呼び出し元の機能  | 無音検出   |  | N | Y    |
| VM | Tenant-Admin機能 | サーバー レベルの保護されたボイスメール    | テナント管理者は、受信ボイスメールを保護済みとしてマークするサービス レベルのルールを構成できます | Y | Y    |
| VM | Tenant-Admin機能 | 記録期間の制限時間を変更する  |     | Y | Y    |
| VM | Tenant-Admin機能 | 無音検出タイムアウトを変更する    |  | 該当なし    | Y    |
| VM | Tenant-Admin機能 | 入力エラーの数を変更する | CVM: 3 にハードコーディング | N | Y    |
| VM | Tenant-Admin機能 | 既定の言語を変更する |  | Y | Y    |
| VM | Tenant-Admin機能 | 文字起こしを無効/有効にする |  | Y | Y    |
| VM | Tenant-Admin機能 | 不在着信通知を無効/有効にする |  | N | Y    |
| VM | Tenant-Admin機能 | Microsoft によるボイス メールのプレビューの改善に役立つ    |  | Y | Y    |
| VM | Tenant-Admin機能 | 有効なユーザーのテキスト メッセージをカスタマイズする|  | 該当なし    | Y    |
| VM | Tenant-Admin機能 | 文字起こしの不適切な表現のマスキング|  | Y | N    |
| VM | Tenant-Admin機能 | ボイスメール ポリシー    |   | Y | Y    |
| VM | Tenant-Admin機能 | Web ポータルの管理   |  | CY19   | Y    |
| VM | Tenant-Admin機能 | PowerShell   |  | Y | Y    |
| UM | ユーザーの機能 | Skype for Business認定された電話でのメッセージ待機インジケーター (MWI)   |電話パートナーが提供する場合があります  | 不要 | はい    |
| AA | サービスの機能 | AA サポートサード パーティ製 PBX    |  | N | Y    |
| AA | サービスの機能 | サポート Skype for Business Server   |  | Y | Y    |
| AA | サービスの機能 | サポート Microsoft Teams|  | Y | N    |
| AA | サービスの機能 | 名前によるダイヤル、DTMF 入力    |  | Y | Y    |
| AA | サービスの機能 | 名前によるダイヤル、音声入力  |  | Y | Y    |
| AA | サービスの機能 | 多言語サポート | ここでの言語の詳細: [クラウドの自動応答とは何ですか?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| AA | サービスの機能 | オペレーター、CQ、またはユーザーに転送する |  | Y | Y    |
| AA | サービスの機能 | 内部で PSTN 番号に転送する (DID RNL)  |  | Y | Y    |
| AA | サービスの機能 | PSTN 番号への外部への転送  |  | 以下の「既知の問題」セクションを確認してください | Y    |
| AA | サービスの機能 | 勤務時間 |  | Y | Y    |
| AA | サービスの機能 | メニュー オプション | IVR メニュー オプション  | Y | Y    |
| AA | サービスの機能 | AA にクラウド PSTN 番号を割り当てる |  | Y | N    |
| AA | サービスの機能 | オンプレミス PSTN 番号を AA に割り当てる  |  | Y | Y    |
| AA | サービスの機能 | カスタム ユーザーの選択  | 呼び出し元が組織ユーザーのカスタマイズされたリストにアクセスできるようにする| Y | Y    |
| AA | サービスの機能 | 時間外および休日の治療  |  | Y | Y    |
| AA | サービスの機能 | テキスト読み上げを使用したカスタムあいさつ  |  | Y | Y    |
| AA | サービスの機能 | 内線ダイヤル   | 拡張機能をダイヤルしてユーザーに連絡する  | Y   | Y    |
| AA | サービスの機能 | AA 呼び出し元がメッセージを残すメールボックス    |  | Y   | Y    |
| AA | サービスの機能 | AA への複数の PSTN 番号の割り当て|  | Y | Y    |
| AA | Tenant-Admin機能 | Web ポータルの管理   |  | Y | N    |
| AA | Tenant-Admin機能 | PowerShell コマンドレット  |  | Y | Y    |
| FAX| サービスの機能 | FAX 統合|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>管理者向けの推奨されるテスト計画と移行後の検証

ユーザーがクラウド ボイスメールに移行されたことを確認するには、ボイスメールをユーザーに任せて、Outlookのメッセージ本文を確認します。 クラウド ボイスメールメッセージには、次を読み取るフッターがあります。

"文字起こしを使用していただきありがとうございます。 上記のトランスクリプトが表示されない場合は、音声の品質が文字起こしに十分明確でなかったためです。

ユーザーの移行後にボイスメール機能をテストする場合は、次のシナリオを考慮してください。

- アプリや IP 電話など、組織内のすべてのエンドポイントの種類にわたるボイスメール アクセスを検証します。
- 構成されたパーソナライズされたあいさつメッセージが呼び出し元に対して再生されることをサンプル ユーザーと共に検証します。
- 組織に、ユーザーの文字起こしを無効にする法的要件またはコンプライアンス要件がある場合は、移行後に無効になっていることを確認します。 詳細については、「[クラウド ボイスメールのセットアップ](/microsoftteams/set-up-phone-system-voicemail)」を参照してください。
- EXCHANGE VM のポリシーとルールを既に構成している場合は、それらが有効であることを確認します。
- ユーザー設定を変更するためのクラウド ボイスメール サービス PowerShell コマンドレットについて理解します。  

### <a name="user-experience-impact"></a>ユーザー エクスペリエンスへの影響

エンド ユーザーボイスメール移行エクスペリエンスの概要を次に示します。


|エクスペリエンス  |ユーザー エクスペリエンスの変更|
|---------|---------|
|メール通知 | 変更なし<br>ボイスメール アカウントのアクティブ化/移行について通知する電子メールはユーザーに送信されません。 |
|以前のメッセージへのアクセス | 変更なし<br>ユーザーは、サポートされているすべてのエンドポイントで以前のボイスメール メッセージにアクセスできます。 |
|Outlook での VM の受信、SFB Apps| 変更なし<br>ユーザーは、サポートされているすべてのエンドポイントでボイスメール メッセージを引き続き受信します。 |
|文字起こし | 強化<br>CVM 文字起こしは、ExchUMO よりもはるかに高い精度率とサポートされている言語を持ちます。 |
|ユーザー設定 | 新しいエクスペリエンス<br>ユーザーは、ユーザー設定ポータル (USP) からユーザー設定を変更できます。 ユーザーは、ボイスメールメールのハイパーリンク、または SFB クライアントの [User-Settings] ボタンから USP にアクセスできます。 https://aka.ms/vmsettings.
 |機能| 詳細については、機能セットの比較を参照してください。 |
|VM メッセージのOutlook規則 | 変更なし<br>以前に作成したルールは、移行後に CVM メッセージに適用されます。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM でのユーザー管理とプロビジョニング

新しいSkype for Business ユーザーは、作成時に Cloud ボイスメールに対して自動的にプロビジョニングされます。 新しいボイスメール ユーザーをプロビジョニングするために追加の管理者の作業またはライセンスは必要ありません。 既存のユーザーと新しいユーザーのポリシー管理については、「[クラウド ボイスメールの設定](/microsoftteams/set-up-phone-system-voicemail)」を参照してください。

### <a name="admin-auto-attendant-management-experience"></a>自動応答管理エクスペリエンスの管理

自動応答の詳細については、「 [クラウド自動応答のセットアップ](/microsoftteams/create-a-phone-system-auto-attendant)」を参照してください。

### <a name="known-issues"></a>既知の問題

#### <a name="greeting-inconsistencies"></a>あいさつ文の不整合

すべてのユーザーがクラウド ボイスメールに移行された後でも、サービスが完全に廃止されるまで、サブスクライバー アクセスはテナントで引き続き機能する可能性があります。 ユーザーの混乱と一貫性のないエクスペリエンスを回避するには、移行後にあいさつ文が変更されるため、サブスクライバーアクセスを無効にします。 これを行うには、. を使用して、各サブスクライバー アクセスラインの EXUM 連絡先を `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`削除します。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>PSTN への自動応答通話転送

Skype for Business ServerのSkype for Business Serverまたは応答グループ サービス (RGS) を介して外部 PSTN 電話番号に自動応答通話を転送するには、PSTN 電話番号または RGS 電話番号に通話転送が設定された新しいオンプレミス ユーザーを作成します。 ユーザーが有効で、エンタープライズ VoIPに対して正しく構成されていて、音声ポリシーが割り当てられている必要があります。

#### <a name="shared-mailbox-is-still-accessible"></a>共有メールボックスに引き続きアクセス可能

EXCHANGE UM Online を使用して構成された共有メールボックスは、CVM への移行後も引き続きメッセージを受信し、Outlook経由でユーザーがアクセスできます。 ただし、これらのメールボックスのあいさつメッセージを変更するためのアクセスは、CVM に移行した後は使用できません。 自動応答の呼び出し元をキャプチャするために使用される共有メールボックスをお持ちのお客様は、自動応答と通話キューの共有メールボックス機能をリリースしたら利用する必要があります (ETA 2019 年 10 月)。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"Username is not using Skype for Business" バナーが表示されます

CVM サービスはMicrosoft Teams インフラストラクチャに基づいており、Skype for Business クライアントからの呼び出しにより、情報バナーがクライアントに表示される可能性があります。"Username はSkype for Businessを使用していません。 より充実したエクスペリエンスを実現するには、Teamsに切り替えるか、Skype会議を開始してください。
このバナーが表示されないように、ユーザーのSkype for Business クライアントを最新の C2R クライアント更新プログラムに更新してください。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"ボイス メールのセットアップ" を実行すると、OWA に移動します

クライアントから **ボイス メールを設定** するをクリックすると、CVM に移行した後、Office Web Access (OWA) ポータル ページに 2015/2013 Skype for Business Server顧客が引き続き移動します。 すべての設定が OWA の [ボイスメール] タブから削除され、CVM ユーザー設定ポータルにユーザーを移動するためのリダイレクト リンクがバナーに表示されます。

#### <a name="changing-greeting-remotely"></a>リモートであいさつを変更する

PSTN サブスクライバー アクセスは CVM ではサポートされていません。 リモートであいさつ文を変更する必要があるユーザーの場合は、モバイル クライアントのボイスメール IVR サービスに [あいさつ文の変更] メニュー オプションが追加されました。 ユーザーは、モバイル クライアントのダイヤル パッドで "1" キーを押したままにして、このサービスを呼び出すことができます。