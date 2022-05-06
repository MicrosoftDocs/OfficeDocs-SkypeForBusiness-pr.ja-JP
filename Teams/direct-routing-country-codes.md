---
title: ダイレクト ルーティングの国コード
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 最適なメディア パスを選択できるように、ダイレクト ルーティングのメディア パスの国コードを見つけるには、この記事を参照してください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36124a8aadc94bfd73ffd195ec8ee0a2acf0c2a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582351"
---
# <a name="direct-routing-media-path-country-codes"></a>ダイレクト ルーティング メディア パスの国コード

メディアのルーティング パスを選択する場合、Direct Routing は既定で、常にセッション ボーダー コントローラー (SBC) のパブリック IP アドレスに基づいてデータセンターを割り当て、SBC データセンターに最も近いパスを常に選択します。

ただし、既定のメディア パスが最適なメディア パスでない場合があります。たとえば、米国範囲のパブリック IP は、ヨーロッパにある SBC に割り当てることができます。 

-MediaRelayRoutingLocationOverride パラメーターをNew-CsOnlinePSTNGatewayおよびSet-CsOnlinePSTNGatewayコマンドレットと共に使用すると、メディア トラフィックの優先リージョンを指定できます。 たとえば、次のコマンドでは、優先リージョンがドイツであることを指定します。

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Microsoft では、メディア パスのデータセンターの既定の割り当てが SBC データセンターに最も近いパスを使用しないことを明確に示す場合にのみ、このパラメーターを設定することをお勧めします。 

> [!NOTE]
> MediaRelayRoutingLocationOverride パラメーターは、マネージド キャリアで使用するために予約されています。
 
## <a name="country-code-reference-table"></a>国コードの参照テーブル

次の表は、-MediaRelayRoutingLocationOverride パラメーターの国コード値を示しています。

| 国         | コード 
|-----------------|--------------------|
| アフガニスタン     | AF |
| Aland Islands   | 斧 |
| アルバニア         | アル |
| アルジェリア         | アルジェリア |
| 米領サモア  | AS |
| アンドラ         | AD |
| アンゴラ          | AO |
| アンギラ        | AI |
| 南極      | AQ | 
| アンティグア バーブーダ | AG |
| アルゼンチン       | AR |
| アルメニア         | 午前 |
| アルバ           | AW |
| オーストラリア       | AU |
| オーストリア         | で |
| アゼルバイジャン      | アリゾナ 州 |
| バハマ         | BS |
| バーレーン         | BH |
| バングラデシュ      | BD |
| バルバドス        | BB |
| ベラルーシ         | BY |
| ベルギー         | BVE |
| ベリーズ          | BZ |
| ベナン           | BJ |
| バミューダ         | BM |
| ブータン          | BT |
| ボリビア         | ボー |
| ボネール         | BQ |
| ボスニア ヘルツェゴビナ | BA |
| ボツワナ        | BW |
| ブーベ島   | BV |
| ブラジル          | BR |
| 英国領インド海洋地域 | IO |
| 英領バージン諸島 | VG |
| ブルネイ          | BN |
| ブルガリア        | BG |
| ブルキナファソ    | BF |
| ブルンジ         | BI |
| カーボ ベルデ      | 品種 |
| カンボジア        | 瀬 |
| カメルーン        | CM |
| カナダ          | CA |
| ケイマン諸島  | ケンタッキー 州 |
| 中央アフリカ共和国 | CF |
| チャド            | TD |
| チリ           | CL |
| 中国           | CN |
| クリスマス島 | CX |
| Cocos (キーリング) 諸島 | CC |
| コロンビア        | CO |
| コモロ         | KM |
| コンゴ           | CG |
| コンゴ (DRC)     | CD |
| クック諸島    | CK |
| コスタリカ      | CR |
| Cote d'Ivoire   | CI |
| クロアチア         | 人事 |
| キューバ            | CU |
| キュラソー         | CW |
| キプロス          | CY |
| チェコ         | CZ |
| デンマーク         | DK |
| ジブチ        | DJ |
| ドミニカ        | DM |
| ドミニカ共和国 | DO |
| エクアドル         | EC |
| エジプト           | EG |
| エルサルバドル     | SV |
| 赤道ギニア | GQ |
| エリトリア         | ER |
| エストニア         | EE |
| Eswatin        | SZ |
| エチオピア        | ET |
| フォークランド諸島 | FK |
| フェロー諸島   | FO |
| フィジー            | FJ |
| フィンランド         | FI |
| フランス          | FR |
| 仏領ギアナ   | GF |
| 仏領ポリネシア | PF |
| フランス領南部地域 | TF |
| ガボン           | ジョージア 州 |
| ガンビア          | GM |
| ジョージア         | GE |
| ドイツ         | DE |
| ガーナ           | GH |
| ジブラルタル       | GI |
| ギリシャ          | GR |
| グリーンランド       | GL |
| グレナダ         | GD |
| グアドループ      | GP |
| グアム            | 区 |
| グアテマラ       | GT |
| ガーンジー        | GG |
| ギニア          | GN |
| Guinea-Bissau   | GW |
| ガイアナ          | GY |
| ハイチ           | こんにちは |
| ハード島と McDonald Islands | HM |
| ホンジュラス        | HN |
| 香港特別行政区   | HK |
| ハンガリー         | HU |
| アイスランド         | は |
| インド           | インチ |
| インドネシア       | ID |
| イラン            | IR |
| イラク            | IQ |
| アイルランド         | IE |
| マン島     | インスタント メッセージ |
| イスラエル          | IL |
| イタリア           | IT |
| ジャマイカ         | JM |
| Jan Mayen       | XJ |
| 日本           | JP |
| ジャージー          | JE |
| ヨルダン          | ジョー |
| カザフスタン      | カザフスタン |
| ケニア           | KE |
| キリバス        | 氣 |
| 韓国           | KR |
| コソボ          | XK |
| クウェート          | KW |
| キルギス      | KG |
| ラオス            | LA |
| ラトビア          | LV |
| レバノン         | ポンド |
| レソト         | LS |
| リベリア         | LR |
| リビア           | LY |
| リヒテンシュタイン   | 李 |
| リトアニア       | 中尉 |
| ルクセンブルク      | LU |
| マカオ特別行政区       | MO |
| マダガスカル      | MG |
| マラウイ          | MW |
| マレーシア        | MY |
| モルディブ        | MV |
| マリ            | ML |
| マルタ           | 山 |
| マーシャル諸島 | MH |
| マルティニーク      | MQ |
| モーリタニア      | 氏 |
| モーリシャス       | MU |
| マヨット         | YT |
| メキシコ          | MX |
| ミクロネシア      | FM |
| モルドバ         | MD |
| モナコ          | MC |
| モンゴル        | ミネソタ |
| モンテネグロ      | 私 |
| モントセラト      | さん |
| モロッコ         | MA |
| モザンビーク      | MZ |
| ミャンマー         | ミリメートル |
| ナミビア         | NA |
| ナウル           | NR |
| ネパール           | NP |
| オランダ     | NL |
| ニューカレドニア   | NC |
| ニュージーランド     | NZ |
| ニカラグア       | NI |
| ニジェール           | NE |
| ナイジェリア         | NG |
| ニウエ            | ニュー |
| ノーフォーク島  | NF |
| 北朝鮮     | KP |
| 北マケドニア | MK |
| 北マリアナ諸島 | NP |
| ノルウェー          | いいえ |
| オマーン            | OM |
| パキスタン        | PK |
| パラオ           | PW |
| パレスチナ自治政府 | PS |
| パナマ          | PA |
| パプアニューギニア | PG |
| パラグアイ        | PY |
| ペルー            | PE |
| フィリピン     | PH |
| Pitcairn Islands | PN |
| ポーランド          | PL |
| ポルトガル        | PT |
| プエルトリコ     | PR |
| カタール           | QA |
| レユニオン         | 再 |
| ルーマニア         | RO |
| ロシア          | RU |
| ルワンダ          | RW |
| サバ            | XS |
| サン バーテレミ | BL |
| セントクリストファー・ネーヴィス | KN |
| セントルシア     | LC |
| サン マルタン島    | MF |
| サン・ピエール島とミケロン島 | PM |
| セントビンセント及びグレナディーン諸島 | VC |
| サモア           | WS |
| サンマリノ      | SM |
| Sao Tome と Principe | 聖 |
| サウジアラビア    | SA |
| セネガル         | SN |
| セルビア          | RS |
| セイシェル      | SC |
| シエラレオネ    | SL | 
| シンガポール       | SG |
| シント ユースタティウス  | XE |
| シント Maarten    | SX |
| スロバキア        | SK |
| スロベニア        | SL |
| ソロモン諸島 | SB |
| ソマリア         | だから |
| 南アフリカ    | 座 |
| サウスジョージアとサウスサンドウィッチ諸島 | GS |
| 南スーダン     | SS |
| スペイン           | ES |
| スリランカ       | LK |
| St Helena、Ascension、Tristan da Cunha | SH |
| スーダン           | SD |
| スリナム        | シニア |
| スバールバル        | SJ |
| スウェーデン          | Standard Edition |
| スイス     | CH |
| シリア           | SY |
| 台湾          | TW |
| タジキスタン      | TJ |
| タンザニア        | TZ |
| タイ        | 番目 |
| Timor-Leste     | TL |
| トーゴ            | TG |
| トケラウ         | TK |
| トンガ           | 宛先 |
| トリニダード・トバゴ | TT |
| チュニジア         | テネシー |
| トルコ          | TR |
| トルクメニスタン    | TM |
| タークス諸島とカイコ諸島 | TC |
| ツバル          | テレビ |
| 米国の離島 | UM |
| 米国領ヴァージン諸島 | VI |
| ウガンダ          | UG |
| ウクライナ         | UA |
| アラブ首長国連邦 | AE |
| 英国  | GB |
| 米国   | 私たち |
| ウルグアイ         | ウルグアイ |
| ウズベキスタン      | UZ |
| バヌアツ         | VU |
| バチカン市国    | バージニア 州 |
| ベネズエラ       | VE |
| ベトナム         | VN |
| Wallis と Futuna | WF |
| イエメン           | あなたがた |
| ザンビア          | ザンビア |
| ジンバブエ        | ZW |
