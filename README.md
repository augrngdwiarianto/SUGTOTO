# SUGTOTOimport React, { useState } from "react";

function App() {
  const [username, setUsername] = useState("");
    const [isLoggedIn, setIsLoggedIn] = useState(false);
      const [credit, setCredit] = useState(1000);
        const [result, setResult] = useState("");

          const handleLogin = () => {
              if (username.trim()) {
                    setIsLoggedIn(true);
                        }
                          };

                            const handleSpin = () => {
                                if (credit < 100) {
                                      setResult("Kredit tidak cukup untuk spin!");
                                            return;
                                                }

                                                    const win = Math.random() > 0.5;
                                                        if (win) {
                                                              setCredit(credit + 200);
                                                                    setResult("Menang! +200 kredit");
                                                                        } else {
                                                                              setCredit(credit - 100);
                                                                                    setResult("Kalah! -100 kredit");
                                                                                        }
                                                                                          };

                                                                                            return (
                                                                                                <div style={{ textAlign: "center", marginTop: "50px", fontFamily: "Arial" }}>
                                                                                                      {!isLoggedIn ? (
                                                                                                              <div>
                                                                                                                        <h1>Selamat Datang di Sugeng Slot</h1>
                                                                                                                                  <input
                                                                                                                                              type="text"
                                                                                                                                                          placeholder="Masukkan username"
                                                                                                                                                                      value={username}
                                                                                                                                                                                  onChange={(e) => setUsername(e.target.value)}
                                                                                                                                                                                              style={{ padding: "10px", fontSize: "16px" }}
                                                                                                                                                                                                        />
                                                                                                                                                                                                                  <br /><br />
                                                                                                                                                                                                                            <button onClick={handleLogin} style={{ padding: "10px 20px", fontSize: "16px" }}>
                                                                                                                                                                                                                                        Login
                                                                                                                                                                                                                                                  </button>
                                                                                                                                                                                                                                                          </div>
                                                                                                                                                                                                                                                                ) : (
                                                                                                                                                                                                                                                                        <div>
                                                                                                                                                                                                                                                                                  <h2>Halo, {username}!</h2>
                                                                                                                                                                                                                                                                                            <h3>Kredit Anda: {credit}</h3>
                                                                                                                                                                                                                                                                                                      <button onClick={handleSpin} style={{ padding: "10px 20px", fontSize: "18px", marginTop: "10px" }}>
                                                                                                                                                                                                                                                                                                                  SPIN
                                                                                                                                                                                                                                                                                                                            </button>
                                                                                                                                                                                                                                                                                                                                      <p style={{ marginTop: "20px", fontWeight: "bold" }}>{result}</p>
                                                                                                                                                                                                                                                                                                                                              </div>
                                                                                                                                                                                                                                                                                                                                                    )}
                                                                                                                                                                                                                                                                                                                                                        </div>
                                                                                                                                                                                                                                                                                                                                                          );
                                                                                                                                                                                                                                                                                                                                                          }

                                                                                                                                                                                                                                                                                                                                                          export default App;