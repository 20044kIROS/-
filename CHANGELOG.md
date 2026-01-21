{
  "language": "ar_YS",
  "DeveloperMode": false,
  "autoCreateDB": true,
  "iconUnsend": {
    "status": true,
    "icon": "💓"
  },
  "notiGroup": false,
  "NOTIFICATION": true,
  "YASSIN": false,
  "allowInbox": true,
  "commandDisabled": [],
  "eventDisabled": [],
  "BOTNAME": "مورو",
  "AMDIN_NAME": "ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ",
  "FACEBOOK_ADMIN": "https://www.facebook.com/akayjy.syjyrwh",
  "PREFIX":"-",
  "ADMINBOT": [ "YourFacebookID" ],
  "NDH": [ "" ],
  "DATABASE": {
    "sqlite": {
      "storage": "data.sqlite"
    }
  },
  "APPSTATEPATH": "appstate.json",
  "FCAOption": {
    "forceLogin": true,
    "listenEvents": true,
    "pauseLog": true,
    "logLevel": "error",
    "selfListen": false,
    "userAgent": "Mozilla/5.0 (iPhone; CPU iPhone OS 15_2 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/15.1 Mobile/15E148 Safari/604.1"
  },
  "version": "1.2.14",
  "menu": {
    "autoUnsend": {
      "status": true,
      "timeOut": 60
    },
    "sendAttachments": {
      "status": true,
      "random": true,
      "url": "./media/fblite_video.mp4"
    }
  },
  "log": {
    "enable": true
  },
  "cave": {
    "cooldownTime": 100000
  },
  "daily": {
    "cooldownTime": 540000,
    "rewardCoin": 500
  },
  "math": {
    "WOLFRAM": "T8J8YV-H265UQ762K"
  },
  "minecraft": {
    "APIKEY": ""
  },
  "randomname": {
    "APIKEY": "mi451266190"
  },
  "subnau": {
    "APIKEY": ""
  },
  "tikinfo": {
    "apikey": "fOeckmtu"
  },
  "xidach": {
    "maxPlayers": 5,
    "normalWinBonus": 1,
    "superWinBonus": 2,
    "epicWinBonus": 4
  },
  "spam": {
    "spamDelay": 2
  },
  "subnautica": {
    "APIKEY": ""
  },
  "adminOnly": false,
  "اوامر": {
    "autoUnsend": true,
    "delayUnsend": 20
  },
  "بنك": {
    "APIKEY": "YourAPIKey"
  },
  "هلب": {
    "autoUnsend": true,
    "delayUnsend": 300
  },
  "تاريخ": {
    "cooldownTime": 200000000
  },
  "الرانك": {
    "autoUnsend": true,
    "unsendMessageAfter": 5
  },
  "كهف": {
    "cooldown": 2000000000
  },
  "لقب": {
    "APIKEY": "YourAPIKey"
  },
  "طقس": {
    "OPEN_WEATHER": "YourOpenWeatherAPIKey"
  }
}import fs from 'fs';

const config = {
  name: "ايموجي",
  aliases: ["guessemoji"],
  version: version,
  description: "لعبة تخمين الأمثال أو الأفلام من خلال الإيموجي.",
  usage: "",
  cooldown: 20,
  permissions: [0],
  credits: "ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ"
};

const puzzles = [
  { question: "🐒👁️‍🗨️🦌", answer: "القرد في عين أمه غزال"},
  { question: "🐦‍⬛➡️🐦‍⬛", answer: "الطيور على أشكالها تقع"},
  { question: "🚢🧊💔", answer: "تيتانيك"},
  { question: "🏃‍♂️💨🇪🇬", answer: "صعيدي في الجامعة الأمريكية"},
  { question: "🐈❤️🐟", answer: "القط يحب خناقه"},
  { question: "✋🔥", answer: "اللي إيده في المية مش زي اللي إيده في النار"},
  { question: "🧠➡️💰", answer: "العقل زينة"},
  { question: "🧅😭", answer: "البصل بيبكي"},
  { question: "🦅🧠", answer: "العقل زينة والغراب شاهد"},
  { question: "🐢🏁", answer: "السلحفاة سبقت الأرنب"},
  { question: "🥛🍚", answer: "رز بلبن"},
  { question: "🧼🧽", answer: "نظافة"},
  { question: "🕷️💃", answer: "رقصة العنكبوت"},
  { question: "🧃🧊", answer: "عصير مثلج"},
  { question: "🧓👶", answer: "من شب على شيء شاب عليه"},
  { question: "🦁👑", answer: "ملك الغابة"},
  { question: "🧳✈️", answer: "شنطة سفر"},
  { question: "🐍🍎", answer: "الثعبان والتفاحة"},
  { question: "🧠💪", answer: "العقل السليم في الجسم السليم"},
  { question: "🧟‍♂️🏃‍♀️", answer: "هروب من الزومبي"},
  { question: "🪞👸", answer: "بياض الثلج"},
  { question: "🧊🧋", answer: "مشروب بارد"},
  { question: "🐓🌅", answer: "صياح الديك عند الفجر"},
  { question: "🧀🐭", answer: "الجبنة والفأر"},
  { question: "🧠🔒", answer: "عقل مغلق"},
  { question: "🦜🗣️", answer: "ببغاء بيقلد"},
  { question: "🧃🍋", answer: "عصير ليمون"},
  { question: "🧊💔", answer: "قلب بارد"},
  { question: "🧠🌀", answer: "تفكير عميق"},
  { question: "🧹🏠", answer: "نظف بيتك"},
  { question: "🧊🧊🧊", answer: "تلج كتير"},
  { question: "🧠🧠🧠", answer: "عقول كثيرة"},
  { question: "🧃🍎", answer: "عصير تفاح"},
  { question: "🧊🧃🍓", answer: "عصير فراولة مثلج"},
  { question: "🧠💡", answer: "فكرة ذكية"},
  { question: "🧠🔥", answer: "دماغ مولعة"},
  { question: "🧠❄️", answer: "دماغ باردة"},
  { question: "🧠🎯", answer: "تركيز عالي"},
  { question: "🧠🧘", answer: "صفاء ذهني"},
  { question: "🧠📚", answer: "دماغ مثقفة"},
  { question: "🧠🎓", answer: "طالب ذكي"},
  { question: "🧠💤", answer: "دماغ نايمة"},
  { question: "🧠😵", answer: "دماغ لفت"},
  { question: "🧠🤯", answer: "دماغ انفجرت"},
  { question: "🧠🤔", answer: "تفكير عميق"},
  { question: "🧠😈", answer: "دماغ شريرة"},
  { question: "🧠😇", answer: "دماغ طيبة"},
  { question: "🧠👻", answer: "دماغ مرعبة"}
];

async function gameReplyHandler({ message, eventData }) {
  const { body, senderID } = message;
  const { answer, gameMessageID } = eventData;
  if (body.toLowerCase() === answer.toLowerCase()) {
    global.api.unsendMessage(gameMessageID);
    const winnerInfo = await global.controllers.Users.getInfo(senderID);
    const winnerName = winnerInfo?.name || senderID;
    await global.controllers.Users.increaseMoney(senderID, 50);
    message.reply(` إجابة صحيحة من ${winnerName}\nالإجابة هي ❴${answer}❵\nلقد ربحت 50 نقطة`);
  }
}

async function onCall({ message }) {
  const randomPuzzle = puzzles[Math.floor(Math.random() * puzzles.length)];
  message.reply(`🤔 خمن المثل أو الفيلم من هذه الإيموجيز:\n\n${randomPuzzle.question}\n\nلديك 30 ثانية للإجابة`)
    .then(sentMessage => {
      sentMessage.addReplyEvent({
        callback: gameReplyHandler,
        answer: randomPuzzle.answer,
        gameMessageID: sentMessage.messageID
      });
      setTimeout(() => {
        global.api.unsendMessage(sentMessage.messageID).catch(() => {});
      }, 30000);
    })
    .catch(err => {
      console.error("خطأ في لعبة الإيموجي:", err);
      message.reply("حدث خطأ أثناء بدء اللعبة.");
    });
}

export default {
  config,
  onCall
};// cmd/nickname.js
const config = require('../config.json');
const log = require('../tools/logger');
const ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ= '▫';
const sleep = ms => new Promise(resolve => setTimeout(resolve, ms));

function toArabicName(name) {
  if (!name) return "";
  let text = name.toLowerCase();
  const complexMap = {
    'th': 'ث',
    'sh': 'ش',
    'ch': 'تْش',
    'ph': 'ف',
    'gh': 'غ',
    'oo': 'و',
    'ee': 'ي',
    'ay': 'ي',
    'ie': 'ي',
    'ue': 'و',
    'qu': 'كْو',
    // التعامل مع حرف 'C' قبل حروف العلة الخفيفة (e, i, y)
    'ce': 'س',
    'ci': 'س',
    'cy': 'س',
    // التعامل مع حرف 'G' قبل حروف العلة الخفيفة (e, i, y)
    'ge': 'ج',
    'gi': 'ج',
    'gy': 'ج',
  };

  // تطبيق التحويلات المعقدة
  for (const [key, value] of Object.entries(complexMap)) {
    // استخدام تعبير منتظم (Regular Expression) مع العلم بحالة الحروف (g)
    text = text.replace(new RegExp(key, 'g'), value);
  }

  // 2. قواعد التحويل لحرف واحد
  const simpleMap = {
    // حروف العلة (Vowels)
    'a': 'ا',
    'e': 'ي',
    'i': 'ي',
    'o': 'و',
    'u': 'و',
    'y': 'ي',
    // الحروف الساكنة (Consonants)
    'b': 'ب',
    'c': 'ك',
    'd': 'د',
    'f': 'ف',
    'g': 'ج',
    'h': 'هـ',
    'j': 'ج',
    'k': 'ك',
    'l': 'ل',
    'm': 'م',
    'n': 'ن',
    'p': 'ب',
    'q': 'ق',
    'r': 'ر',
    's': 'س',
    't': 'ت',
    'v': 'ف',
    'w': 'و',
    'x': 'كس',
    'z': 'ز',
    // للحفاظ على المسافات
    ' ': ' ',
    '-': '-',
  };

  // تطبيق التحويلات البسيطة
  return text.split("").map(c => simpleMap[c] || c).join("");
}

// دالة لإضافة رمز الجنس حسب البيانات
function getGenderEmoji(gender) {
  if (!gender) return "";
  const g = gender.toLowerCase();
  if (g === "male") return "🚹";
  if (g === "female") return "🚺";
  if (g === "no specific gender" || g === "other") return "🚻";
  return "";
}

module.exports = {
  name: 'كنيات',
  otherName: ['كنيه', 'nickname'],
  rank: 1,
  cooldown: 5,
  type: 'المجموعة',
  run: async (api, event, args) => {
    const { threadID, messageID, body } = event;
    if (args.length === 0) {
      return api.sendMessage(
        `لصيغة: كنية البوت كنية عام <القالب>`,
        threadID,
        messageID
      );
    }

    // ======================================
    // تغيير كنية البوت
    // ======================================
    if (args[0] === "بوت") {
      const newNickname = config?.BOTNAME;
      if (!newNickname) {
        return api.sendMessage(
          ` لا توجد قيمة BOTNAME داخل config.json."مورو"
          threadID,
          messageID
        );
      }
      try {
        const botID = await api.getCurrentUserID();
        await api.nickname(newNickname, threadID, botID);
        return api.sendMessage(
          `${ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ} تم تعيين كنية البوت : ${newNickname}`,
          threadID,
          messageID
        );
      } catch (err) {
        log?.error("BOT Nickname Error:", err);
        return api.sendMessage(
          `فشل تغيير كنية البوت.\n${err.message}`,
          threadID,
          messageID
        );
      }
    }

    // ======================================
    // gc لتغيير كنيات أعضاء المجموعة
    // ======================================
    if (args[0] === "الكل" || args[0] === "عام") {
      const template = args.slice(1).join(" ");
      if (!template || !template.includes("الاسم")) {
        return api.sendMessage(
          `يجب أن يحتوي القالب على كلمة (الاسم).`,
          threadID,
          messageID
        );
      }
      try {
        const threadInfo = await api.getThreadInfo(threadID);
        const members = threadInfo.userInfo || [];
        const botID = await api.getCurrentUserID();
        api.sendMessage(
          `⏳ جاري تطبيق الكنيات على ${members.length} عضو...`,
          threadID,
          messageID
        );
        for (const member of members) {
          const userID = member.id;
          if (userID === botID) continue; // منع تغيير اسم البوت
          const fullName = member.name || member.firstName || "User";
          const firstName = toArabicName(fullName.split(" ")[0]);
          const genderEmoji = getGenderEmoji(member.gender);
          // استبدال الاسم والجنس في أي مكان داخل القالب
          const finalNickname = template
            .replace(/الاسم/g, firstName)
            .replace(/الجنس/g, genderEmoji);
          try {
            await api.nickname(finalNickname, threadID, userID);
            await sleep(700);
          } catch (e) {
            log?.error("Member Nickname Error:", e);
          }
        }
        return api.sendMessage(
          `${ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ} تم تطبيق الكنيات بنجاح!`,
          threadID
        );
      } catch (err) {
        log?.error("GC Nickname Error:", err);
        return api.sendMessage(
          `${ᏆᎬᏁᎶᎬᏁ ᏚᎯᎷᎯ} ⚠️ فشل تعديل الكنيات.\n${err.message}`,
          threadID,
          messageID
        );
      }
    }
    return api.sendMessage(
      `خيار غير صحيح. استخدم: كنية bot كنية عام <القالب>`,
      threadID,
      messageID
    );
  }
};
