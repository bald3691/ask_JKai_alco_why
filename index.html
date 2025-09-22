import os
from flask import Flask, render_template, request, jsonify

app = Flask(__name__)

# Wzorce - każdy w osobnej zmiennej żeby uniknąć błędów składni
WZORZEC_F = "Wykonaj analizę w trybie 'Protokół Równowagi Ciała - 72 godziny'. Odpowiadaj opisowo i konkretnie.\n\nA. SYGNAŁY ALARMOWE (BEZPIECZEŃSTWO)\nSprawdź czy pojawiają się objawy wymagające natychmiastowej pomocy medycznej - drżenia, wymioty, omdlenia, ból w klatce piersiowej. Oceń czy występuje poważne odwodnienie, brak snu dłużej niż półtorej doby, głodzenie dłużej niż dobę. Określ czy istnieje ryzyko dla siebie lub innych. Jeśli tak - opisz natychmiastowy krok i do kogo się zwrócić.\n\nB. RYTM TRZECH DNI\nOpisz wzorce z ostatnich trzech dni: ile godzin snu każdej nocy, jak długo trwało zasypianie, ile posiłków dziennie, jak silne było uczucie głodu i pragnienia, ile czasu poświęcono na ruch, jak intensywny był ból. Pokaż co się powtarza, co się pogarsza, gdzie są największe deficyty.\n\nC. ŁAŃCUCH OD CIAŁA DO IMPULSU\nOpisz jak konkretny brak w ciele (sen, jedzenie, ruch) prowadzi do emocji, a ta do impulsu sięgnięcia po substancję. Pokaż tę sekwencję krok po kroku z przykładami z sytuacji.\n\nD. CO DZIEJE SIĘ W ORGANIZMIE\nWyjaśnij jak niedobory wpływają na naturalne rytmy ciała - adenozyna i melatonina przy braku snu, kortyzol przez całą dobę, hormony głodu i sytości, dopamina reagująca na substancje. Pokaż jak używanie substancji zaburza te naturalne procesy.\n\nE. PLAN PRZYWRACANIA RÓWNOWAGI - TRZY POZIOMY CZASOWE\nTeraz (najbliższa godzina): trzy konkretne czynności do wykonania od razu, wyjaśnij po co każda.\nDziś (do końca dnia): trzy działania z opisem jak sprawdzić czy się udały.\nNajbliższe trzy dni: trzy cele z opisem jak je mierzyć w codziennym życiu.\n\nF. PYTANIA DO AUTOREFLEKSJI\nJak bardzo zmęczone jest ciało, jak bardzo odwodnione, jak bardzo spięte. Trzy pytania o codzienne rutyny związane ze snem, jedzeniem i ruchem - co działa, co nie działa, co można zmienić."

WZORZEC_P = "Wykonaj analizę w trybie 'Emocje, Schematy Myślowe i Małe Eksperymenty na 14 dni'.\n\nA. KLUCZOWE MYŚLI\nWyłuskaj trzy zdania z opisu sytuacji, które najlepiej pokazują sposób myślenia - te momenty, gdzie widać automatyczne skojarzenia i wnioski.\n\nB. PRZECIĘCIA EMOCJI I SCHEMATÓW MYŚLOWYCH\nOpisz jak strach, wstyd i złość łączą się z dwoma podstawowymi przekonaniami: 'nie potrafię sobie poradzić' oraz 'nie jestem wystarczająco dobry'. Pokaż jak każde z tych przecięć tworzy charakterystyczny sposób odbierania rzeczywistości. Strach połączony z bezradnością wygląda inaczej niż strach z poczucia własnej bezwartości.\n\nC. OBECNY STAN WEWNĘTRZNY\nOpisz słowami obecny nastrój, jak natarczywe są powtarzające się myśli, jak duża jest zdolność do znoszenia nieprzyjemnych stanów oraz jak silne jest pragnienie ulgi.\n\nD. CO DZIEJE SIĘ W MÓZGU\nKrótko wyjaśnij jak wzorzec zachowania wpływa na naturalne systemy uspokojenia i nagrody. Jak zakłóca naturalne procesy radzenia sobie ze stresem i dlaczego tworzy się błędne koło.\n\nE. PIĘĆ MAŁYCH EKSPERYMENTÓW NA NAJBLIŻSZE DWA TYGODNIE\nZaproponuj pięć konkretnych, małych prób do przeprowadzenia w codziennym życiu. Każdy z jasno określonym: co dokładnie robić, kiedy i gdzie, oraz jak poznać że próba się powiodła. Eksperymenty powinny być małe żeby nie przerażały, ale konkretne żeby dały prawdziwe informacje o innych sposobach reagowania."

WZORZEC_R = "Wykonaj analizę w trybie 'Mapa Relacji i Dwa Skrypty Rozmów na 7 dni'.\n\nA. MAPA LUDZI I RÓL\nOpisz kluczowe osoby z sytuacji oraz ich role. Pokaż kto od kogo czego oczekuje, w którą stronę płynie pomoc, gdzie są żądania, gdzie wsparcie. Stwórz słowny obraz sieci powiązań.\n\nB. BILANS DAWANIA I BRANIA\nOceń opisowo: ile dajesz w porównaniu do tego ile otrzymujesz, jak jasne są granice w kontaktach, jak często dochodzi do konfliktów i eskalacji. Gdzie jest nierównowaga, gdzie brakuje jasności.\n\nC. WZORZEC RELACYJNY JAKO PALIWΟ DLA NAŁOGU\nWyjaśnij jak konkretny sposób bycia w relacjach (ucieczka, atak, zadowalanie wszystkich) napędza potrzebę sięgania po substancje. Pokaż ten mechanizm na przykładach z sytuacji.\n\nD. NEUROBIOLOGIA WIĘZI I KONFLIKTU\nKrótko opisz jak układy przywiązania w mózgu reagują na relacyjny stres - hormony więzi, system alarmowy, reakcje na odrzucenie. Jak to wpływa na pragnienie ulgi."

WZORZEC_T = "Wykonaj analizę w trybie 'Okno Wytrzymałości Emocjonalnej - stabilizacja w 48 godzin'. Priorytet: bezpieczeństwo i stabilizacja.\n\nA. MAPA OBJAWÓW I ICH INTENSYWNOŚCI\nOpisz czy i jak często pojawiają się: powracające obrazy z przeszłości, koszmary, nagłe zamrożenie, silne unikanie. Jak długo trwają te stany i ile czasu potrzeba na powrót do normy. Użyj opisów zamiast liczb - 'bardzo słabe', 'umiarkowane', 'przytłaczające'.\n\nB. STREFY FUNKCJONOWANIA\nOpisz przykłady z sytuacji dla trzech stanów: Strefa nadmiernego pobudzenia: kiedy system alarmowy pracuje na najwyższych obrotach - walka lub ucieczka. Strefa odrętwienia: kiedy wszystko się wyłącza - zamrożenie, brak uczuć, automatyczne funkcjonowanie. Strefa optymalnego funkcjonowania: kiedy można myśleć i czuć jednocześnie, reagować adekwatnie."

WZORZEC_X = "Wykonaj analizę w trybie 'Mapa Bodźców i Reguły Jeśli-To na cykl dobowy i tygodniowy'.\n\nA. SEKWENCJE BODZIEC-REAKCJA-SKUTEK\nOpisz pięć najważniejszych sekwencji z codziennego życia: Bodziec (co się dzieje w otoczeniu) prowadzi do Reakcji (impuls, myśl, emocja) i kończy się Skutkiem (co ostatecznie robisz). Pokaż całą ścieżkę słowami, nie używaj schematów ani tabel.\n\nB. RANKING SIŁY WPŁYWU I DOSTĘPNOŚCI\nOpisz które bodźce mają największy wpływ na uruchamianie nawyku, a które są najbardziej dostępne w codziennym otoczeniu. Połącz te dwie informacje - co jest jednocześnie silne i łatwo dostępne."

# Słownik wzorców
WZORCE = {
    'F': {
        'opis_grupy': "Grupa F: Równowaga ciała i podstawowe potrzeby – sen, odżywianie, nawodnienie, ruch, ból, regeneracja.",
        'wzorzec': WZORZEC_F
    },
    'P': {
        'opis_grupy': "Grupa P: Świat wewnętrzny - emocje, sposoby myślenia, rozmowa z sobą, znoszenie trudności.",
        'wzorzec': WZORZEC_P
    },
    'R': {
        'opis_grupy': "Grupa R: Świat relacji - role, granice, sposób komunikacji, dawanie i branie wsparcia.",
        'wzorzec': WZORZEC_R
    },
    'T': {
        'opis_grupy': "Grupa T: Trudne doświadczenia z przeszłości - nadmierne pobudzenie, odrętwienie, unikanie, granice wytrzymałości.",
        'wzorzec': WZORZEC_T
    },
    'X': {
        'opis_grupy': "Grupa X: Otoczenie i wyzwalacze - ludzie, miejsca, pory dnia, reklamy, rytuały które uruchamiają nawyk.",
        'wzorzec': WZORZEC_X
    }
}

# Dostępne modele (testowe)
AVAILABLE_MODELS = {
    "test-model": {
        "name": "Model Testowy",
        "api_type": "test",
        "free": True
    }
}

def build_prompt(fala_text, grupa):
    """Buduje pełny prompt łącząc FALA z wzorcem grupy"""
    if grupa not in WZORCE:
        raise ValueError(f"Nieznana grupa: {grupa}")
    
    wzorzec_data = WZORCE[grupa]
    opis = wzorzec_data['opis_grupy']
    pattern = wzorzec_data['wzorzec']
    
    prompt_parts = [
        f"Grupa GUZ: {grupa}",
        f"FALA: {fala_text}",
        "",
        f"Opis grupy: {opis}",
        "",
        pattern
    ]
    
    return "\n".join(prompt_parts)

@app.route('/')
def home():
    return render_template('instructions.html')

@app.route('/fala')
def fala_page():
    return render_template('fala.html', models=AVAILABLE_MODELS)

@app.route('/analyze', methods=['POST'])
def analyze():
    try:
        data = request.json
        fala_text = data.get('fala', '').strip()
        grupa = data.get('grupa', '')
        model_key = data.get('model', '')
        
        if not fala_text or len(fala_text) < 10:
            return jsonify({"error": "FALA musi mieć co najmniej 10 znaków"}), 400
            
        if grupa not in WZORCE:
            return jsonify({"error": "Nieprawidłowa grupa"}), 400
            
        if model_key not in AVAILABLE_MODELS:
            return jsonify({"error": "Nieprawidłowy model"}), 400
        
        # Buduj prompt (wzorzec ukryty przed użytkownikiem)
        full_prompt = build_prompt(fala_text, grupa)
        
        # Testowa odpowiedź AI
        response_text = f"TESTOWA ANALIZA AI dla grupy {grupa}:\n\n"
        response_text += f"Przeanalizowałem Twoją FALĘ pod kątem {WZORCE[grupa]['opis_grupy']}\n\n"
        response_text += f"Twoja FALA: '{fala_text[:100]}...'\n\n"
        response_text += "To jest przykładowa odpowiedź. Gdy podłączysz prawdziwe API, tutaj pojawi się pełna analiza AI na podstawie ukrytego wzorca.\n\n"
        response_text += f"Długość wygenerowanego promptu (niewidoczna dla Ciebie): {len(full_prompt)} znaków"
        
        return jsonify({
            "success": True,
            "response": response_text,
            "model_used": AVAILABLE_MODELS[model_key]["name"],
            "grupa": grupa
        })
        
    except Exception as e:
        return jsonify({"error": f"Błąd serwera: {str(e)}"}), 500

@app.route('/test')
def test():
    return f"Serwer działa! Załadowane grupy: {list(WZORCE.keys())}"

if __name__ == '__main__':
    # Lokalny development
    app.run(debug=True, host='127.0.0.1', port=5001)
else:
    # Production na hostingu
    print("Aplikacja uruchomiona na hostingu")