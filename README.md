import React, { useState } from "react";
import About2 from "./About2";

export default function About() {
  const [isShow, setIsShow] = useState(false);
  const [isOfferAccept, setIsOfferAccept] = useState(false);

  const handleOpenModel = () => {
    setIsShow(true);
  };

  const handleCloseModel = () => {
    setIsShow(false);
  };

  const handleOfferAccept = () => {
    setIsOfferAccept(true);
    setIsShow(false);
  };
  return (
    <div>
      <div className="show-offer">
       { !isOfferAccept&& <button onClick={handleOpenModel} className="offer-btn">
          Show Offer
        </button>}
        {
          isOfferAccept&&<div className="text-6xl font-bold text-pink-400">Offer Accepted</div>
        }
      </div>

      {isShow && <About2 handleCloseModel={handleCloseModel} handleOfferAccept={handleOfferAccept} />}
    </div>
  );
}

